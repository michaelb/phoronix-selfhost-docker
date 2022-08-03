FROM phoronix/pts:latest

RUN apt-get update &&\
   apt-get install php-sqlite3 -y

ADD user-config.xml /etc/phoronix-test-suite.xml



EXPOSE 9090 9091 9092

VOLUME ["/var/cache/phoronix-test-suite/download-cache/", "/var/lib/phoronix-test-suite/phoromatic"]

CMD /phoronix-test-suite/phoronix-test-suite start-phoromatic-server
