FROM phoronix/pts:latest

RUN apt-get update &&\
   apt-get install php-sqlite3 -y && \
   apt-get install iproute2 -y

EXPOSE 9090 9091 9092

VOLUME ["/var/cache/phoronix-test-suite/download-cache/", "/var/lib/phoronix-test-suite/phoromatic"]

CMD /phoronix-test-suite/phoronix-test-suite phoromatic.connect $PHOROMATIC_SERVER_IP:$PHOROMATIC_SERVER_PORT/$PHOROMATIC_SERVER_USER_HASH
