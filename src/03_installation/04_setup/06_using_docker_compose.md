# Using Docker Compose

You can create a file named `compose.yml` based on the example below.

```yml
version: "3"

services:
  hyperbase-mqtt:
    container_name: hyperbase-mqtt
    image: docker.io/emqx:5
    restart: unless-stopped
    networks:
      - hyperbase-network
    ports:
      - "8883:8883"
      - "1883:1883"
      - "9083:8083"
      - "9084:8084"
      - "18083:18083"
    volumes:
      - ./volume/hyperbase-mqtt/data:/opt/emqx/data:Z

  hyperbase-db-pg:
    container_name: hyperbase-db-pg
    image: docker.io/postgres:16
    restart: unless-stopped
    networks:
      - hyperbase-network
    ports:
      - "5432:5432"
    env_file:
      - config.pg.env
    volumes:
      - ./volume/hyperbase-db-pg:/var/lib/postgresql/data:Z

  hyperbase:
    container_name: hyperbase
    image: docker.io/mnaufalhilmym/hyperbase
    restart: unless-stopped
    networks:
      - hyperbase-network
    ports:
      - "15511:8080"
    volumes:
      - ./config.yml:/app/config.yml:R
      - ./volume/hyperbase-bucket:/app/hyperbase_bucket:Z
    depends_on:
      - hyperbase-mqtt
      - hyperbase-db-pg

  hyperbase-ui:
    container_name: hyperbase-ui
    image: docker.io/mnaufalhilmym/hyperbase-ui
    restart: unless-stopped
    networks:
      - hyperbase-network
    ports:
      - "3000:3000"
    depends_on:
      - hyperbase
```

To run the Docker compose, execute this command.

```console
$ docker compose up
```

> **NOTE**: You can also run Docker compose in detached mode (run containers in the background) by using -d or --detach option.
