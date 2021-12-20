FROM debian:buster
WORKDIR /var/www/html
RUN apt-get update && apt-get install -y wget php-fpm vim unzip 
RUN wget http://wordpress.org/latest.tar.gz
COPY ./config/wp-config.php ./wordpress
RUN tar -xzvf latest.tar.gz && \ 
# mv /home/jkate/inception/srcs/requirements/wordpress/wp-config.php ./wordpress/ && \
# chown www-data:www-data /var/www/html && \
find /var/www/html -exec chown www-data:www-data {} + && \
find /var/www/html -type d -exec chmod 2775 {} + && \
find /var/www/html -type f -exec chmod 0664 {} +
# chmod -R 2775 /var/www/html 
# VOLUME vol1
EXPOSE 9000
ENTRYPOINT ["/bin/bash", "-c", "/usr/sbin/php-fpm7.3"]
ENTRYPOINT ["tail", "-f"] 