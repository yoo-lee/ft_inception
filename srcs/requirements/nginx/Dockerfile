#install alpine
FROM debian:latest

#install all the program
RUN apt-get update
RUN apt-get install -y openssl

#nginx SSL
RUN mkdir /etc/nginx/ssl
RUN openssl req -newkey rsa:4096 -x509 -sha256 -days 365 -nodes \
       -out /etc/nginx/ssl/vbachele.crt \
       -keyout /etc/nginx/ssl/vbachele.key \
       -subj "/C=JP/ST=Tokyo/L=Tokyo/O=42 School/OU=yoo-lee/CN=yoo-lee/"


COPY ./default.conf /etc/nginx/conf.d

#nginx config
RUN mkdir -p /run/nginx

EXPOSE 443

#start nginx
CMD ["nginx", "-g",  "daemon of;"]

