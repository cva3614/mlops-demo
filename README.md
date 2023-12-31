# End-to-end-Machine-Learning-Project-with-MLflow


## Workflows

1. Update config.yaml
    - Remains inside config directory.
    - Use to create all the artifacts like downloading, extracting, train-test split, validation status, evaluation metrics.
    - Define all the value such as url, storing path, loading path etc.
    - These value can be mapped using config_entity which later can be access from related components.

2. Update schema.yaml
    - Remains at root directory.
    - Used to validate the schema of our data by verifying the list of columns that are used to build the model.
    - Any changes to our data such as adding new column or removing old columns results to schema validation fail.

3. Update params.yaml
    - Remains inside config directory.
    - Use to setup parameters for our model in this file.
    - Makes us easy to compare between different values of parameters.

4. Update the entity
    - Remains inside entity directory which is named as cofing_entity.
    - These config_entity maps all the values from config.yaml
    - We have to map with same name in both config.yaml and inside config_entity @dataclass

5. Update the configuration manager in src config
    - Remains inside src/mlops_demo/config
    - Define functions that are used to get data from config.yaml using config_entity.
    - Returns respective config_entity such as DataIngestionConfig, DataValidationConfig etc.

6. Update the components
    - Remains inside src/mlops_demo/components.
    - Use to create all the required components that work on specific task.
7. Update the pipeline 
    - Remains inside src/mlops-demo/pipeline.
    - Use to automate all the components seamlessly.
    - 
8. Update the main.py
9. Update the app.py



# How to run?
### STEPS:

Clone the repository

```bash
https://github.com/entbappy/End-to-end-Machine-Learning-Project-with-MLflow
```
### STEP 01- Create a conda environment after opening the repository

```bash
conda create -n mlproj python=3.8 -y
```

```bash
conda activate mlproj
```


### STEP 02- install the requirements
```bash
pip install -r requirements.txt
```


```bash
# Finally run the following command
python app.py
```

Now,
```bash
open up you local host and port
```



## MLflow

[Documentation](https://mlflow.org/docs/latest/index.html)


##### cmd
- mlflow ui

### dagshub
[dagshub](https://dagshub.com/)

MLFLOW_TRACKING_URI=https://dagshub.com/entbappy/End-to-end-Machine-Learning-Project-with-MLflow.mlflow \
MLFLOW_TRACKING_USERNAME=entbappy \
MLFLOW_TRACKING_PASSWORD=6824692c47a369aa6f9eac5b10041d5c8edbcef0 \
python script.py

Run this to export as env variables:

```bash

export MLFLOW_TRACKING_URI=https://dagshub.com/entbappy/End-to-end-Machine-Learning-Project-with-MLflow.mlflow

export MLFLOW_TRACKING_USERNAME=entbappy 

export MLFLOW_TRACKING_PASSWORD=6824692c47a369aa6f9eac5b10041d5c8edbcef0

```



# AWS-CICD-Deployment-with-Github-Actions

## 1. Login to AWS console.

## 2. Create IAM user for deployment

	#with specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	#Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	#Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
## 3. Create ECR repo to store/save docker image
    - Save the URI: 566373416292.dkr.ecr.ap-south-1.amazonaws.com/mlproj

	
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
	#optinal

	sudo apt-get update -y

	sudo apt-get upgrade
	
	#required

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker
	
# 6. Configure EC2 as self-hosted runner:
    setting>actions>runner>new self hosted runner> choose os> then run command one by one


# 7. Setup github secrets:

    AWS_ACCESS_KEY_ID=

    AWS_SECRET_ACCESS_KEY=

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

    ECR_REPOSITORY_NAME = simple-app




## About MLflow 
MLflow

 - Its Production Grade
 - Trace all of your expriements
 - Logging & tagging your model


