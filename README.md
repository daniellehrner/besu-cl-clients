# Besu / CL client docker compose setup

## Initial setup 
#### Create the JWT secret
```
openssl rand -hex -out secret/token.txt 32
```

## Start Besu-Teku
```
docker-compose -f docker-compose-teku.yml up
```

## Start Besu-Prysm
```
docker-compose -f docker-compose-prysm.yml up
```

## Start Besu-Nimbus
#### Initial setup
The following command needs to be run once to do a checkpoint sync
```
docker run -v ${PWD}/data/nimbus:/opt/nimbus/data statusim/nimbus-eth2:amd64-latest trustedNodeSync --data-dir=/opt/nimbus/data --network=sepolia --trusted-node-url=https://sepolia.checkpoint-sync.ethpandaops.io
```

Afterwards start it with:
```
docker-compose -f docker-compose-nimbus.yml up
```
