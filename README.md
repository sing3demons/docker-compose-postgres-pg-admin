# docker-compose-postgres-pg-admin
```
version: "3.8"

services:
  postgres:
    image: postgres
    container_name: some-postgres
    ports:
      - 5432:5432
    environment:
      - POSTGRES_DB=pg-api
      - POSTGRES_USER=postgres
      - POSTGRES_PASSWORD=syspass
    volumes:
      - ./data:/var/lib/postgresql/data
    restart: always
  pgadmin:
    image: dpage/pgadmin4
    environment:
      - PGADMIN_DEFAULT_EMAIL=sing3demons@live.com
      - PGADMIN_DEFAULT_PASSWORD=SuperSecret
    ports:
      - 8081:80
```
<hr/>
```
version: "3.8"

services:
  postgres:
    image: postgres
    container_name: some-postgres
    ports:
      - 5432:5432
    environment:
      - POSTGRES_DB=${PG_DB}
      - POSTGRES_USER=${PG_USER}
      - POSTGRES_PASSWORD=${PG_PASSWORD}
    volumes:
      - ./data:/var/lib/postgresql/data
    restart: always
  pgadmin:
    image: dpage/pgadmin4
    environment:
      - PGADMIN_DEFAULT_EMAIL=sing3demons@live.com
      - PGADMIN_DEFAULT_PASSWORD=SuperSecret
    ports:
      - 8081:80
      
```

```
.env
```
```
PG_DB=pg-api
PG_USER=postgres
PG_PASSWORD=syspass
```
