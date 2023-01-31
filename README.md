# dockerized_vre

## Install and run

docker-compose build
docker-compose up

## Fixes:

In container sgecore:

docker exec -it sgecore /bin/bash
qconf -mconf (change UID from 1000 to 0)

## Rellevant cmd
#### Connecting to mongoDB using a local mongo-visualizer via websocket
ssh -i key.pem -L localhost:27017:192.168.0.198:27017 ubuntu@84.88.189.135
 

## TODO
- shared_data esta en local
- header fixed but pending to test
