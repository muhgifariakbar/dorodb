# dorodb

## Project Structures

- Layout

```
.
├── app.env.sample ( contains application configuration )
├── cmd ( main binary )
├── Makefile ( simplify project commands )
├── docs ( swagger documentation )
├── db
│   └── migrations ( database migrations )
└── internal
    ├── app
    │   ├── controllers ( request response handler )
    │   ├── models ( all about database table )
    │   ├── repository ( database/cache operation )
    │   ├── router ( http router )
    │   ├── schema ( request/response schema )
    │   └── service ( business logic )
    └── pkg ( private lib )
```

## how to run

create docker-compose.yml file
docker compose up -d
docker ps : untuk cek container yang jalan
docker exec -it dorodb-db-1 bin/bash : psql -U postgres -d postgres : \l untuk cek psql >> untuk list db dan query >> list db dalam container yang pernah dijalaninin

create db/migration
set migrate di yaml

## Migration Commands

1. Create migration file

```
make migrate-create name=migration_name
```

2. Migrate Down / Rollback migration

```
make migrate-down
```

3. Migrate UP / Applt migration to database

```
make migrate-up
```
