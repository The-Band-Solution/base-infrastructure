# Register on Debezium

## 🚀 Goal

Provides an example of configuration of a database using Debezium. 


## 🔧 Background 

A register a file that contains the Debezium's configurations to read data in a database`s table.

```json

{
    "name": "application_configuration-connector",
    "config": {
        "connector.class": "io.debezium.connector.postgresql.PostgresConnector",
        "tasks.max": "1",
        "database.hostname": "db-pg",
        "database.port": "5432",
        "database.user": "postgres",
        "database.password": "postgres",
        "database.dbname" : "application_configuration",
        "topic.prefix": "application_configuration",
        "topic.partitions": 3,
        "schema.include.list": "public"
    }
}

```
Parameters:

1) **name**: name of configuration on Debezium
2) **connector.class**: classe used to connect a database (e.g., We are using PostgresSQL and, thus, we used io.*debezium.connector.postgresql.PostgresConnector*.) 
3) task.max: number of task used to read table modifications;

4) **database.hostname**: Database`s hostname. (e.g., Localhost).

5) **database.port**: Database`s port ("5432").

6) **database.user**: Database`s username (e.g., postgres).

7) **database.password**: Database`s password (e.g., postgres).

8) **database.dbname** : database`s name (e.g., application_configuration)

9) **topic.prefix**: topic prefix (e.g., application_configuration).

10) **topic.partitions**: number of particions in a kafka`s topic(e.g., 3)

11) **schema.include.list**: a list of schema that will be used to scan by debezium (e.g., "public")

## 🔧 Command 

1. Add a regiter:


```bash

curl -i -X POST -H "Accept:application/json" -H  "Content-Type:application/json" http://localhost:8083/connectors/ -d @register-application_configuration.json

```

1. Remove a regiter:

```bash
curl -i -X DELETE localhost:8083/connectors/application_configuration-connector/
```

## 📕 Literature

1. [Debezium GitHub Examples](https://github.com/debezium/debezium-examples/tree/main/tutorial)

2. [Introduction to Debezium](https://www.baeldung.com/debezium-intro)









