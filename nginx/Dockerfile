FROM nginx:alpine
RUN apk update && apk add nano curl dos2unix

# Remove any existing config files
RUN rm /etc/nginx/conf.d/*

COPY ./nginx.conf.template /etc/nginx/conf.d/nginx.conf.template

COPY ./entrypoint.sh /entrypoint.sh

RUN dos2unix /entrypoint.sh && chmod +x /entrypoint.sh && chmod 644 /etc/nginx/conf.d/nginx.conf.template

# Expose the listening port
EXPOSE 80 443

# Launch NGINX
ENTRYPOINT ["/entrypoint.sh"]