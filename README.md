# Teku - Besu docker compose setup

1. Create the JWT secret
```
openssl rand -hex 32 -out secret/token.txt
```

2. Start the clients with
```
docker-compose up
```