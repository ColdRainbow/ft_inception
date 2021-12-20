FROM nginx:latest 

RUN apt-get update && apt-get install -y wget nginx openssl

COPY conf /etc/nginx/conf.d/conf 

COPY ./init.sh /opt/init.sh

VOLUME /var/log/nginx/log/

RUN chmod 777 /opt/init.sh

EXPOSE 443 

CMD /opt/init.sh
