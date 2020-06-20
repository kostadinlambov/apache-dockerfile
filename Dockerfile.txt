FROM ubuntu:20.04
LABEL maintainer="KL"
RUN echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections
RUN apt-get update -y && apt-get install -y apache2 && apt-get clean
RUN rm -f /var/www/html/index.html 
COPY index.html /var/www/html
CMD ["apachectl", "-D", "FOREGROUND"]
EXPOSE 80