# Alfresco 6 Profiling with Docker and VisualVM

This project includes PostgreSQL **profiling** for Alfresco Community 6.2 using [pg_stat_statements](https://www.postgresql.org/docs/11/pgstatstatements.html) extension

# How to use this composition

## Start Docker

Start docker and check the ports are correctly bound.

```bash
$ docker-compose up --build --force-recreate
```

## Access

Use the following username/password combination to login in Alfresco services.

 - User: admin
 - Password: admin

Alfresco and related web applications can be accessed from the below URIs when the servers have started.

```
http://localhost/share         - Alfresco Share WebApp
http://localhost/alfresco      - Alfresco Repository (REST)
http://localhost/solr          - Alfresco Search Services (Basic Auth, admin/admin by default)
```

## Profiling

Start an interactive SSH session with Postgres Docker Container

```bash
$ docker exec -it postgres_postgres_1 sh
```

Use `psql` to init the extension.

```sql
# psql -U alfresco

alfresco=# CREATE EXTENSION pg_stat_statements;

alfresco=# SELECT pg_stat_statements_reset();
```

Once initialized, queries will be saved in the table `pg_stat_statements` so you can get different metrics from your database.

```sql
alfresco=# \d pg_stat_statements;
                    View "public.pg_stat_statements"
       Column        |       Type       | Collation | Nullable | Default
---------------------+------------------+-----------+----------+---------
 userid              | oid              |           |          |
 dbid                | oid              |           |          |
 queryid             | bigint           |           |          |
 query               | text             |           |          |
 calls               | bigint           |           |          |
 total_time          | double precision |           |          |
 min_time            | double precision |           |          |
 max_time            | double precision |           |          |
 mean_time           | double precision |           |          |
 stddev_time         | double precision |           |          |
 rows                | bigint           |           |          |
 shared_blks_hit     | bigint           |           |          |
 shared_blks_read    | bigint           |           |          |
 shared_blks_dirtied | bigint           |           |          |
 shared_blks_written | bigint           |           |          |
 local_blks_hit      | bigint           |           |          |
 local_blks_read     | bigint           |           |          |
 local_blks_dirtied  | bigint           |           |          |
 local_blks_written  | bigint           |           |          |
 temp_blks_read      | bigint           |           |          |
 temp_blks_written   | bigint           |           |          |
 blk_read_time       | double precision |           |          |
 blk_write_time      | double precision |           |          |
```
