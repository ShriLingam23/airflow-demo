# Airflow Docker Setup

This guide will walk you through setting up Apache Airflow using Docker.

## Step 1: Prepare Directories & Login Information

First, create the necessary directories and set up the environment variables.
```markdown
$ mkdir Airflow && cd Airflow
$ mkdir -p ./dags ./logs ./plugins
$ echo -e "AIRFLOW_UID=$(id -u)" > .env
```

## Step 2: Fetch docker-compose.yaml file

Download the `docker-compose.yaml` file from the official Apache Airflow documentation.

```sh
$ curl -LfO 'https://airflow.apache.org/docs/apache-airflow/2.5.0/docker-compose.yaml'
$ tree
.
├── dags
├── docker-compose.yaml
├── logs
└── plugins
```

## Step 3: Initialize Airflow

This command only needs to be run on your first initiation of the Airflow service. It will set up the environment for you and create an admin user for you to log in with.

```sh
$ docker compose up airflow-init
```

## Step 4: Run Docker Compose Up

Now that the Airflow environment has been initiated, we can launch it with the following command. The `-d` specifies detached mode.

```sh
$ docker compose up -d
```

## Step 5: Check Status of Containers

Verify that the containers are running.

```sh
$ docker ps
```

## Step 6: Visit the Airflow Web Interface

Open your browser and go to [http://localhost:8080](http://localhost:8080). The default credentials are `airflow/airflow`.
```

Ref : https://medium.com/@ericfflynn/my-journey-with-apache-airflow-d7d364fc84ba