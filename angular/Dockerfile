FROM nginx:1.23.1-alpine

COPY nginx.conf /etc/nginx/nginx.conf
COPY dist/angular-starter /usr/share/nginx/html

WORKDIR /app

#---switch to non root user---
RUN chown -R nginx:nginx /app && chmod -R 755 /app && \
        chown -R nginx:nginx /var/cache/nginx && \
        chown -R nginx:nginx /var/log/nginx && \
        chown -R nginx:nginx /etc/nginx/conf.d
RUN touch /var/run/nginx.pid && \
        chown -R nginx:nginx /var/run/nginx.pid

USER nginx
#---

EXPOSE 8080