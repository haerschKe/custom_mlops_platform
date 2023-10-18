# CUSTOM MLOPS PLATFORM
**Simple MLOps platform with MLFlow, Airflow and Grafana/Prometheus.**


Each component has a separate subfolder with its code and configuration. In **example_model_dvc** is an example of an SGD Classifier with Imagenette160 dataset and DVC handling (with local remote storage).

There is an example DAG which logs into the MLFlow under an "Demo" Experiment.

The MLFow and Airflow Containers are in the same docker network, although they are configured in two different docker-compose files (just for better structuring).
The network is created in the MLFlow compose file, while the airflow compose file refers to the created network.

There is an custom Airflow Dockerfile which is used for the compose stuff. The Dockerfile only adds the requirements.txt for the airflow instance.

## How to run:
Go to the project root directory.

Start MLFow: 
docker-compose -f mlflow_docker/docker-compose.yaml up -d

Start Airflow: docker-compose -f airflow_docker/docker-compose-airflow.yaml up -d

## Credentials
Airflow Login: User "airflow", PW "airflow" --> default values of Airflow Docker Config

## TODO:
- Grafana/Prometheus
