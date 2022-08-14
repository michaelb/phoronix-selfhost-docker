# Phoromatic server & client in docker


## Run the server

```
$ cd ./server
$ docker build .
5f846.....      # <-- image ID

$ docker  run -d \
          -p 9090:9090 \   # <- websocket, optionnal, may be needed for external triggers(?)
          -p 9091:9091 \   # <- phoromatic webUI
          -p 9092:9092 \   # <- Result viewer
          --name phoromatic-server \
          5f846    # <- image ID
```


## Run the client(s)

(you can run one or more :-) )

```
$ cd ./client
$ docker build .
abc123....    # <- server image ID

$ docker run -d --name phoronix-client \
             -e PHOROMATIC_SERVER_IP="192.168.X.Y" \   # <- docker host IP, optionnal
             -e PHOROMATIC_SERVER_PORT=9091 \          # <- exposed port for phoromatic webUI, optionnal
             -e PHOROMATIC_SERVER_USER_HASH="123ABC" \ # <- hash for phoromatic user ID, shown on phoromatic homepage after registration/login
             abcd123  # <- server image ID

```

NB: you can replace the phoromatic_server_ip host IP by the name 'phoromatic-server' if both dockers are on the same custom network
