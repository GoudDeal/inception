FROM debian:buster
RUN apt-get update \
&& apt-get -y upgrade \ 
&& apt-get -y install apt-utils nginx openssl

COPY ./nginx.conf  /etc/nginx/sites-available/default

# ADD index.html /var/www/wordpress

RUN openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/dcyprien.key -out /etc/ssl/dcyprien.pem -subj "/C=FR/ST=./L=Paris/O=dcyprien=./CN=dcyprien.42.fr"

EXPOSE 443

ENTRYPOINT ["nginx", "-g", "daemon off;"]
