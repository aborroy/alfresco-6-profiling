# Alfresco 6 Profiling with Docker and YourKit

This project includes [YourKit Java Profiler](https://www.yourkit.com/download/) profiling for Alfresco Community 6.2. This product requires using a paid license.

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

Open [YourKit Java Profiler](https://www.yourkit.com/download/) app and configure the endpoints:

* **Alfresco Repository** service is available in `localhost:10002`
* **Search Service** service is available in `localhost:10001`
