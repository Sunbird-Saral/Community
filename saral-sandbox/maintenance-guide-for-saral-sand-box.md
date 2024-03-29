# Maintenance Guide for Saral Sandbox-Environment

Purpose -&#x20;

This guide is created to help teams to maintain sandbox in ready to use clean condition for the demo purposes.

1. Mongo DB collections clean up

During Demo large amount of sample data will be created which is no use post demo and to other demo users. Hence, it becomes necessary to clean such test data.  This is 2 step process where in first step current data will be deleted and in next step, fresh test data will be loaded for demo purposes. Please use below commands in sequence for clean up of data.

1. &#x20;To delete any old data from database run the following command in the VM where the sandbox app is installed. Execute below command in the terminal of your VM where docker is installed.

```
docker exec sandbox node ./data/import-data.js --delete
```

2. &#x20;To add golden data to the database run the following command in the VM where the sandbox app is installed. Execute below command in the terminal of your VM where docker is installed.

```
docker exec sandbox node ./data/import-data.js --import
```

2. Logging and Monitoring

Saral application stack has been enabled with logging and monitoring. Click [here](https://tekdi-docs.netlify.app/docs/learning/grafana/) for details on installation and setup guide

3. Click [here](https://docs.google.com/document/d/1T0x8RWGHxG578rytLDTivA1bducZYwUTl\_VYwYLmLcs/edit#heading=h.q7kutkgpepnj) for troubleshooting guide on Docker and Docker Compose. This will also lists steps to check connection issue between Mongo DB and Backend Service.



