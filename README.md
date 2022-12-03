# Konnector Database

## What is this repository for?

Managing the Konnector database

## How do I get set up?

* Create a Maven master password `$ mvn --encrypt-master-password`
* Store the encrypted master password in ~/.m2/settings-security.xml
```
<settingsSecurity>
    <master>{password}</master>
</settingsSecurity>
```
* Encrypt the database schema password `$ mvn --encrypt-password`
* Store the encrypted password in ~/.m2/settings.xml under the servers element
```
<settings>
    <servers>
        <server>
            <id>konnector_database</id>
            <username>root</username>
            <password>{password}</password>
        </server>
    </servers>
</settings>
```

## Running liquibase

* Navigate to the project root
* Run `$ mvn clean compile liquibase:update -DdatabaseName=konnector_test`
* Default databaseName is konnector
