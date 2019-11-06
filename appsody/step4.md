# Build and deploy your Appsody project

The Appsody CLI provides various options to help you with the transition from the development phase to the deployment phase:

You can use the `appsody build `command to generate a deployment Docker image on your local Docker registry, and then manually deploy that image to your runtime platform of choice.

You can use the `appsody deploy `command to deploy the same deployment Docker image directly to a Kubernetes cluster that you are using for testing or staging.

You can also delegate the build and deployment steps to an external pipeline, such as a Tekton pipeline that consumes the source code of your Appsody project after you push it to a GitHub repository. In this case, you can use `appsody deploy --generate-only `to generate a deployment manifest, which you can then push to your repo.

### Build your runtime Docker image

When you use the Appsody CLI to develop your applications, a *development* container image of the target runtime is downloaded and run for you. This image differs slightly from the image that is used at deployment time, because it configures tools that are useful only during the development phase.

In order to generate the *deployment* container image execute `appsody build`{{execute interrupt}} command in the terminal (make sure you've terminated the development container from the previous step).

The `appsody build` command completes the following actions:

1. Extracts your code and other artifacts, including a new Dockerfile, which are required to build the *deployment* image from the *development* image. These files are saved to the `~/.appsody/extract` directory.

2. Runs a `docker build `against the Dockerfile that was extracted on the previous step to produce a deployment image in your local Docker registry. If you want to give the image a name, specify the `-t <tag>` parameter. If you run appsody build with no parameters, the image is given a name that matches the name of your project.

Verify the deployment image was created:

`docker images | grep my-project`{{execute}}

You will deploy your application to a Kubernets cluster in the next step.
