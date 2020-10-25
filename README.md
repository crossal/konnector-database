# Konnector Database

## What is this repository for?

Managing the Konnector database

## How do I get set up?

* Create a Maven master password `$ mvn --encrypt-master-password`
* Store the encrypted master password in ~/.m2/settings-security.xml
* Encrypt the database schema password `$ mvn --encrypt-password`
* Store the encrypted password in ~/.m2/settings.xml under the servers element
```
<server>
    <id>id</id>
    <username>username</username>
    <password>{passoword}</password>
</server>
```

## Running liquibase

* Navigate to the project root
* Run `$ mvn clean compile liquibase:update`
