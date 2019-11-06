# Deploying your app to a Kubernetes cluster

There are many options to deploy your Appsody applications to a Kubernetes cluster. The best approach depends on the specific scenario:

If you are testing your app on a locally installed cluster, using `appsody deploy` is your best bet.

If you intend to have your app deployed on a shared cluster for integration testing or production, you are probably going to rely on CI/CD pipelines, and have the app built and deployed from its source.

The `appsody deploy` command provides a way for you to deploy your application directly to a Kubernetes cluster.


If the stack contains a deployment manifest that can be consumed by the [Appsody operator](https://operatorhub.io/operator/appsody-operator), `appsody deploy` will install the operator, if necessary, and deploy your application to the cluster using that deployment manifest.
If the stack you are using is not equipped with the manifest for the Appsody operator, appsody deploy attempts to install your app as a Knative serving service.

Execute the following command to deploy your project into a Kubernetes cluster with the Appsody operator:

`appsody deploy`{{execute interrupt}}

Check the operator and your new application deployment in Kubernetes:

`kubectl get all`{{execute}}

Get the service NodePort so we can access the application externally:

`export NODE_PORT=$(kubectl get service my-project -o go-template='{{(index .spec.ports 0).nodePort}}')
echo NODE_PORT=$NODE_PORT`{{execute}}

Test the output of your Kubernetes application deployment:

`curl https://[[HOST_SUBDOMAIN]]-$NODE_PORT-[[KATACODA_HOST]].environments.katacoda.com/`{{execute}}

You have succesfully deployed your cloud-native application!
