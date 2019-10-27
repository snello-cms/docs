---
description: >-
  Rendertron is a dockerized, headless Chrome rendering solution designed to
  render & serialise web pages on the fly. It's mandatary to SEO rendering for
  spider.
---

# Rendertron

```text
server {
        listen 80;
        listen [::]:80;

        server_name website.com www. website.com;
        return 302 https://$server_name$request_uri;
}

server {
 	gzip on;
 	gzip_disable "msie6";
 	gzip_vary on;
 	gzip_proxied any;
 	gzip_comp_level 6;
 	gzip_buffers 16 8k;
 	gzip_http_version 1.1;
 	gzip_types text/plain text/css application/json application/x-javascript text/xml application/xml application/xml+rss text/javascript;

        listen 443 ssl;
        listen [::]:443 ssl;

        server_name website.com www. website.com;


        ssl_certificate /etc/ssl/website.com.crt;
        ssl_certificate_key /etc/ssl/website.com.key;


        location / {
            root /usr/share/nginx/html;
            index index.html index.htm;
            try_files $uri @prerender;
        }



        location /api/ {
            proxy_pass  http://website/api/; # rest-api
            proxy_redirect     off;
            proxy_set_header   Host             $host;
            proxy_set_header   X-Real-IP        $remote_addr;
            proxy_set_header   X-Forwarded-For  $proxy_add_x_forwarded_for;

            # this is the maximum upload size
            client_max_body_size 10M;
            client_body_buffer_size    16K;
        }

        location /login {
            proxy_pass  http://website/; # rest-api
            proxy_redirect     off;
            proxy_set_header   Host             $host;
            proxy_set_header   X-Real-IP        $remote_addr;
            proxy_set_header   X-Forwarded-For  $proxy_add_x_forwarded_for;

            # this is the maximum upload size
            client_max_body_size 10M;
            client_body_buffer_size    16K;
        }

        location @prerender {
            root /usr/share/nginx/html;
            index index.html index.htm;

            set $prerender 0;
            if ($http_user_agent ~* "googlebot|bingbot|yandex|baiduspider|twitterbot|facebookexternalhit|rogerbot|linkedinbot|embedly|quora link preview|showyoubot|outbrain|pinterest|slackbot|vkShare|W3C_Validator|XML Sitemaps Generator|Google-Structured-Data-Testing-Tool|Screaming Frog SEO") {
                set $prerender 1;
            }
            if ($args ~ "_escaped_fragment_") {
                set $prerender 1;
            }
            if ($http_user_agent ~ "Prerender") {
                set $prerender 0;
            }
            if ($uri ~* "\.(js|css|xml|less|png|jpg|jpeg|gif|pdf|doc|txt|ico|rss|zip|mp3|rar|exe|wmv|doc|avi|ppt|mpg|mpeg|tif|wav|mov|psd|ai|xls|mp4|m4a|swf|dat|dmg|iso|flv|m4v|torrent|ttf|woff|svg|eot)") {
                set $prerender 0;
            }

            if ($prerender = 1) {
                set $prerender "rendertron";
                rewrite .* /render/$scheme://$host$request_uri? break;
                proxy_pass http://rendertron;
            }
            if ($prerender = 0) {
               rewrite .* /index.html break;
               #try_files $uri $uri/ /index.html =404;
            }
        }
}

upstream website {
     server website:8080;
}

upstream rendertron {
     server rendertron:80;
}

```

{% embed url="https://github.com/GoogleChrome/rendertron" %}

{% embed url="https://webmasters.googleblog.com/2019/01/dynamic-rendering-with-rendertron.html" %}

{% embed url="https://itnext.io/using-rendertron-in-kubernetes-for-spa-seo-39055567c745" %}



