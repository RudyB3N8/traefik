# Traefik

## Initialize

> Rename .env.exemple to .env

Use command to initialize.

```bash
docker-compose up -d --build
```

OR

```bash
docker-compose up -p "<project_name>" -d --build
```

## Configuration

For adding a new service, in its "docker-compose.yml" put these lines

```yml
labels:
    - "traefik.enable=true"
    - "traefik.http.routers.apache.entrypoints=websecure"
    - "traefik.http.routers.apache.rule=Host(`domain`)"
    - "traefik.http.routers.apache.tls.certresolver=lets-encr"
```