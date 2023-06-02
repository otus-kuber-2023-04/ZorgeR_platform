FROM nginx

COPY . /

RUN usermod -u 1001 nginx && \
    groupmod -g 1001 nginx

RUN echo "server {" > /etc/nginx/conf.d/default.conf && \
    echo "    listen 8000;" >> /etc/nginx/conf.d/default.conf && \
    echo "    location / {" >> /etc/nginx/conf.d/default.conf && \
    echo "        root   /app;" >> /etc/nginx/conf.d/default.conf && \
    echo "        index  index.html index.htm;" >> /etc/nginx/conf.d/default.conf && \
    echo "    }" >> /etc/nginx/conf.d/default.conf && \
    echo "}" >> /etc/nginx/conf.d/default.conf

EXPOSE 8000

CMD ["nginx", "-g", "daemon off;"]
