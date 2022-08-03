FROM phoronix/pts:latest

# default host IP for main docker network on Linux
ENV PHOROMATIC_SERVER_IP=172.17.0.1

# default phoromatic port
ENV PHOROMATIC_SERVER_PORT=9091

RUN apt-get update &&\
   apt-get install php-sqlite3 -y && \
   apt-get install iproute2 -y

VOLUME ["/var/cache/phoronix-test-suite/download-cache/", "/var/lib/phoronix-test-suite/phoromatic"]

CMD /phoronix-test-suite/phoronix-test-suite phoromatic.connect $PHOROMATIC_SERVER_IP:$PHOROMATIC_SERVER_PORT/$PHOROMATIC_SERVER_USER_HASH
