FROM nginx:1.27.0

RUN apt update
RUN apt -y install vim

# /usr/share/nginx/html/index.html
COPY index.html /usr/share/nginx/html/index.html
RUN chown nginx:nginx /usr/share/nginx/html/index.html