# DynamoDB Note

**To start dynamodb locally**
```
$ java -Djava.library.path=./DynamoDBLocal_lib -jar DynamoDBLocal.jar -sharedDb
```

**To delete table**
```
$ aws dynamodb delete-table --table-name Posts
```
