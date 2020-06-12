# CLI: PSQL

Psql is the interactive terminal for working with Postgres. Theres an abundance of flags available for use when working with psql, but lets focus on some of the most important ones, then how to connect

#### Connect psql by peer
```shell
cd /usr/bin
su postgres
psql
```

#### Connect psql from remote
Enable the remote connection of PostgreSQL, then connect it
```shell
psql -U postgre -h localhost -W
```

