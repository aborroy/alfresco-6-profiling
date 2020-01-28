# Alfresco 6 Profiling with Docker

This project includes different **profiling** methods when using Docker Compose deployments with Alfresco Community 6.2.

* [visual-vm](/visual-vm) is profiling Alfresco Repository and Alfresco Search Services using [VisualVM](https://visualvm.github.io)
* [yourkit](/yourkit) is profiling Alfresco Repository and Alfresco Search Services using [YourKit Java Profiler](https://www.yourkit.com/download/). This product requires using a paid license.
* [postgres](/postgres) is profiling PostgreSQL database using [pg_stat_statements](https://www.postgresql.org/docs/11/pgstatstatements.html) extension

Note that some other tools are available for profiling Alfresco, like [Elastic APM](https://www.zylk.net/en/web-2-0/blog/-/blogs/using-elastic-apm-for-alfresco-performance-monitoring)

These configurations are **not** intended to be used in production systems, as they have impact in performance.
