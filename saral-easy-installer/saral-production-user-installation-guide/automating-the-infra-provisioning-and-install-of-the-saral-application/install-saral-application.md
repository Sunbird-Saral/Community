# Installing the Saral Application

Once the entire Infrastructure is setup

We need to update the application with the **"document db hostname", "username", "password" and the "ssl certificate arn".**

1. Go to the following folder "Saral-Automation/Saral-EKS/helm/saral-backend-chart/"
2. Fill the value.yml file with the following details

```
a. under docdb->connections-> fill documentdb username, documentdb password, documentdb hostname
b. under whitelist->domain-> fill in your domain/subdomain 
c. under ingress->certificateARN-> fill the certificate arn that you will get from AWS certificate manager
```

Once you have updated the values in the `value.yml` file, use the following command to deploy the chart

Open the helm folder in a terminal window and run the following

Below command will deploy the application to your Kubernetes cluster using the values you have specified in the values.yml file

```
helm install saral-backend ./saral-backend-chart
```

Verify the deployment by checking the status of the pods.

```
kubectl get pods
```

You should see the pods associated with your deployment running successfully



To uninstall the `saral-backend` deployment using Helm, execute the following command

```
helm uninstall saral-backend
```
