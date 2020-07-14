# DynamoDB Note


## DynamoDB Set up

### Local DynamoDB Set up
1. Download DynamoDB.zip file from [AWS DynamoDB page](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBLocal.DownloadingAndRunning.html).

2. Unzip the zip file downloaded and redirect a current directory to DynamoDB local folder.

3. Run a command below to start up the DynamoDB locally.
   ```shell
   $ java -Djava.library.path=./DynamoDBLocal_lib -jar DynamoDBLocal.jar -sharedDb
   ```
### DynamoDB Set up with Docker
1. Download [Docker Desktop](https://www.docker.com/products/docker-desktop).

2. Create a docker-compose.yml file.
   ```yml
   version: '3.7'
   services:
    dynamodb-local:
      image: amazon/dynamodb-local:latest
      container_name: dynamodb-local
      ports:
       - "8000:8000"
   ```

3. Start the docker by run the following command-line.
   ```shell
   $ docker-compose up
   ```
   
   
### DynamoDB Admin Set up
1. Install [dynamodb-admin](https://www.npmjs.com/package/dynamodb-admin) by run the following command-line.
   ```shell
   $ npm install -g dynamodb-admin
   ```

2. Run the dynamodb-admin by run the following command-line.
   ```shell
   # For Windows
   $ set DYNAMO_ENDPOINT=http://localhost:8000
   $ dynamodb-admin
   ```
   ```shell
   # For Mac/Linux
   $ export DYNAMO_ENDPOINT=http://localhost:8000
   $ dynamodb-admin
   ```

### AWS Credential Set up
1. Install [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-windows.html).

2. Create AWS Credential by run the following command-line.
   ```shell
   $ aws configure
   ```
