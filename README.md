
# Postgres / Postgis container

Purpose: creation of standard Postgres postgis development environment to avoid version conflicts 

## Based on [kartoza/postgis:12.4](https://hub.docker.com/layers/kartoza/postgis/12.4/images/sha256-21aa19ff2df3832a039f1455d93bd15b00135c47042c6c40663f3085a8e0e84d?context=explore) Docker container application.


```git clone repository https://github.com/robinsonbrz/postgres-12-postgis-3-dev.git```


### Building the container
````docker-compose  -f docker-compose.prod.yml up -d --build````

A new container named ***dev_pg_12*** is created and running


### Accessing container psql
````psql -h localhost -p 25432 postgres````



## Restore database procedure

```
psql -h localhost -p 25432 postgres
```
```sql

postgres=# 

CREATE DATABASE nome_do_banco;
\q
```

### Restoring from postgres sql dump file
```psql -h localhost -p 25432 -U postgres pacto < pacto.sql\n```

### Restoring from postgres dump file
```pg_restore -h localhost -p 25432 -U postgres -d nome_do_banco nome_do_banco.dump```

### Connect to Dbeaver or PgAdmin using the port: 25432

# Setting up Projects - .env file
 
.env file change the 
DB_PORT=25432



### Connect to container - optional
````docker exec -ti dev_pg_12 bash````




