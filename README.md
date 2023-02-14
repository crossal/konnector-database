# Konnector Database

## What is this repository for?

Managing the Konnector database

## How do I get set up?

* Install Maven

## Running liquibase

* Navigate to the project root
* Run `$ mvn clean compile liquibase:update`

## Running in a MySQL Docker container

* Install Docker

### Locally

* Run `$ docker run --publish 3306:3306 --name konnector-database -e MYSQL_DATABASE='konnector_test' -e MYSQL_ROOT_PASSWORD='password' -d mysql:8.0.31-debian`
* Run `$ mvn clean compile liquibase:update -DdatabaseName=konnector_test`

### Production

* Run `$ docker run --publish 3306:3306 --name konnector-database -e MYSQL_DATABASE='konnector' -e MYSQL_ROOT_PASSWORD='<password>' -d mysql:8.0.31-debian` (if RAM is constrained, arguments like `--memory 400m --memory-swap 5G` can also be provided)
* Run `$ mvn clean compile liquibase:update -DdatabaseName=konnector -DdatabasePassword='<password'`
* Consider removing the previous commands from the history by running something like `history -d $(history 2)` for Linux


* To remove any stopped containers and all unused images `$ docker system prune -a`
