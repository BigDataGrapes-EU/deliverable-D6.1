# Docker Compose

![N|Solid](https://github.com/docker/compose/raw/master/logo.png?raw=true)

Compose is a tool for defining and running multi-container Docker applications.
With Compose, you use a Compose file to configure your application's services.
Then, using a single command, you create and start all the services
from your configuration. To learn more about all the features of Compose
see [the list of features](https://github.com/docker/docker.github.io/blob/master/compose/overview.md#features).

Compose is great for development, testing, and staging environments, as well as
CI workflows. You can learn more about each case in
[Common Use Cases](https://github.com/docker/docker.github.io/blob/master/compose/overview.md#common-use-cases).

Using Compose is basically a three-step process.

1. Define your app's environment with a `Dockerfile` so it can be
reproduced anywhere.
2. Define the services that make up your app in `docker-compose.yml` so
they can be run together in an isolated environment.
3. Lastly, run `docker-compose up` and Compose will start and run your entire app.

A `docker-compose.yml` looks like this:

    version: '2'

    services:
      web:
        build: .
        ports:
         - "5000:5000"
        volumes:
         - .:/code
      redis:
        image: redis

For more information about the Compose file, see the
[Compose file reference](https://github.com/docker/docker.github.io/blob/master/compose/compose-file/compose-versioning.md).

Compose has commands for managing the whole lifecycle of your application:

 * Start, stop and rebuild services
 * View the status of running services
 * Stream the log output of running services
 * Run a one-off command on a service

Installation and documentation
------------------------------

- Full documentation is available on [Docker's website](https://docs.docker.com/compose/).
- Code repository for Compose is on [GitHub](https://github.com/docker/compose).

Install Compose on Linux systems
------------------------------
On Linux, you can download the Docker Compose binary from the [Compose repository release page on GitHub](https://github.com/docker/compose/releases). Follow the instructions from the link, which involve running the `curl` command in your terminal to download the binaries. These step by step instructions are also included below

1. Run this command to download the latest version of Docker Compose:
```sh
$ sudo curl -L https://github.com/docker/compose/releases/download/1.18.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
```
2. Apply executable permissions to the binary:
```sh
$ sudo chmod +x /usr/local/bin/docker-compose
```
3. Optionally, install [command completion](https://docs.docker.com/compose/completion/) for the `bash` and `zsh` shell.
4. Test the installation.
```sh
$ docker-compose --version
docker-compose version 1.18.0, build fdd22a9
```


List of Docker Images
------------------------------


| Component | Location |
| ------ | ------ |
| Graphdb | [bigdatagrapes/graphdb](https://cloud.docker.com/u/bigdatagrapes/repository/docker/bigdatagrapes/graphdb) |
| Sparkling-water | [bigdatagrapes/sparklingwater](https://cloud.docker.com/u/bigdatagrapes/repository/docker/bigdatagrapes/sparklingwater) |
| Virtuoso | [bigdatagrapes/virtuoso](https://cloud.docker.com/u/bigdatagrapes/repository/docker/bigdatagrapes/virtuoso) |
| Neo4j | [bigdatagrapes/neo4j](https://cloud.docker.com/u/bigdatagrapes/repository/docker/bigdatagrapes/neo4j) |
| Hbase | [bigdatagrapes/hbase](https://cloud.docker.com/u/bigdatagrapes/repository/docker/bigdatagrapes/hbase) |
| Kafka | [bigdatagrapes/kafka](https://cloud.docker.com/u/bigdatagrapes/repository/docker/bigdatagrapes/kafka) |
| Flink | [bigdatagrapes/flink](https://cloud.docker.com/u/bigdatagrapes/repository/docker/bigdatagrapes/flink) |
| Flume | [bigdatagrapes/flume](https://cloud.docker.com/u/bigdatagrapes/repository/docker/bigdatagrapes/flume) |
| Kibana | [bigdatagrapes/kibana](https://cloud.docker.com/u/bigdatagrapes/repository/docker/bigdatagrapes/kibana) |
| Elasticsearch | [bigdatagrapes/elasticsearch](https://cloud.docker.com/u/bigdatagrapes/repository/docker/bigdatagrapes/elasticsearch) |
| Spark-master | [bigdatagrapes/spark-master](https://cloud.docker.com/u/bigdatagrapes/repository/docker/bigdatagrapes/spark-master) |
| Spark-worker | [bigdatagrapes/spark-worker](https://cloud.docker.com/u/bigdatagrapes/repository/docker/bigdatagrapes/spark-worker) |
| Hadoop | [bigdatagrapes/hadoop](https://cloud.docker.com/u/bigdatagrapes/repository/docker/bigdatagrapes/hadoop) |
| PhpMyAdmin | [bigdatagrapes/phpmyadmin](https://cloud.docker.com/u/bigdatagrapes/repository/docker/bigdatagrapes/phpmyadmin) |
| Mysql | [bigdatagrapes/mysql](https://cloud.docker.com/u/bigdatagrapes/repository/docker/bigdatagrapes/mysql) |
| Tomcat | [bigdatagrapes/tomcat](https://cloud.docker.com/u/bigdatagrapes/repository/docker/bigdatagrapes/tomcat) |
| Cassandra | [bigdatagrapes/cassandra](https://cloud.docker.com/u/bigdatagrapes/repository/docker/bigdatagrapes/cassandra) |
| Mongo | [bigdatagrapes/mongo](https://cloud.docker.com/u/bigdatagrapes/repository/docker/bigdatagrapes/mongo) |
|Logstash| [bigdatagrapes/logstash](https://cloud.docker.com/u/bigdatagrapes/repository/docker/bigdatagrapes/logstash) |


## Deployment

To help with the deployment of the stack there are 2 scripts present:
* _deploy.sh_, that deploys the whole stack, and
* _destroy.sh_, that clears everything running as a docker container in the VM executed.

Both these scripts should be executed as root.
