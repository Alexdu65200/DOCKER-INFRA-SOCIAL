FROM nginx

RUN rm /etc/nginx/conf.d/default.conf

RUN apt-get update -y
RUN apt-get install curl -y
RUN curl -sLo /usr/local/bin/ep https://github.com/kreuzwerker/envplate/releases/download/v0.0.8/ep-linux && chmod +x /usr/local/bin/ep

COPY wordpress.nginx.conf /etc/nginx/conf.d/wordpress.nginx.conf
COPY backdoor.nginx.conf /etc/nginx/conf.d/backdoor.nginx.conf

CMD /usr/local/bin/ep -v /etc/nginx/conf.d/*.conf & nginx -g "daemon off;"