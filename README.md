# ETL

## Architecture Diagram
<img width="554" alt="Screen Shot 2022-02-03 at 02 52 41" src="https://user-images.githubusercontent.com/40035682/152268317-c77eff7b-9105-4948-9538-00de8870ce11.png">

## Demo 

Apache Superset dashboard credentials:
```
username: admin
password: admin
```

* Airbyte front-end: http://soufianeodf.tech:8000
* Apache Superset: http://soufianeodf.tech:8080

# Requirements

* Docker

# Getting Started

## 1- Clone repository

```
git clone https://github.com/soufianeodf/virtuocode-w1-etl.git etl

cd etl
```

## 2- Run docker compose in detached mode
```
docker-compose up -d
```

## 3- With your local superset container already running...

* 1- Setup your local admin account

    ```
    docker exec -it superset superset fab create-admin \
                   --username admin \
                   --firstname Superset \
                   --lastname Admin \
                   --email admin@superset.com \
                   --password admin
    ```

* 2- Migrate local DB to latest

    ```
    docker exec -it superset superset db upgrade
    ```

* 3- Load Examples (Optional)

    ```
    docker exec -it superset superset load_examples
    ```

* 4- Setup roles
    ```
    docker exec -it superset superset init
    ```
    
* 5- Install BigQuery Driver and restart superset container
    ```
    docker-compose exec superset pip install pybigquery
    docker-compose restart superset
    ```
