# Alfresco 6 Profiling with Docker and VisualVM

This project includes [VisualVM](https://visualvm.github.io) **profiling** for Alfresco Community 6.2.

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

Open [VisualVM](https://visualvm.github.io) app and configure the JMX endpoints:

* **Alfresco Repository JMX** service is available in `jmx://localhost:9091`
* **Search Service JMX** service is available in `jmx://localhost:9090`
