# DynamoDB Note


## DynamoDB Set up

### Local DynamoDB Set up
1. Download DynamoDB.zip file from [AWS DynamoDB page](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBLocal.DownloadingAndRunning.html).

2. Unzip the zip file downloaded and redirect a current directory to DynamoDB local folder.

3. Run a command below to start up the DynamoDB locally.
   ```
   $ java -Djava.library.path=./DynamoDBLocal_lib -jar DynamoDBLocal.jar -sharedDb
   ```
### DynamoDB Set up with Docker
1. Download [Docker Desktop](https://www.docker.com/products/docker-desktop).

2. Create a docker-compose.yml file.
   ```
   version: '3.7'
   services:
    dynamodb-local:
      image: amazon/dynamodb-local:latest
      container_name: dynamodb-local
      ports:
       - "8000:8000"
   ```

3. Start the docker by run the following command-line.
   ```
   $ docker-compose up
   ```
