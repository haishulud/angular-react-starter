#FROM node:18.7.0-alpine3.15 as node
#WORKDIR /app
#COPY . .
#RUN npm install
#RUN npm run build

FROM nginx:1.23.1-alpine
#COPY --from=node /app/dist/angular-starter /usr/share/nginx/html
RUN echo $(ls)
RUN echo $ls
RUN echo $pwd
RUN ls
RUN ls /home
RUN ls /home/runner
RUN ls /home/runner/work
RUN ls /home/runner/work/angular-react-starter
RUN ls /home/runner/work/angular-react-starter/angular-react-starter
RUN ls /home/runner/work/angular-react-starter/angular-react-starter/angular
RUN ls /home/runner/work/angular-react-starter/angular-react-starter/angular/dist
RUN ls /home/runner/work/angular-react-starter/angular-react-starter/angular/dist/angular-starter
ENTRYPOINT ["ls"]
COPY /home/runner/work/angular-react-starter/angular-react-starter/angular/dist/angular-starter /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf
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