# Create a project

Creating a new Appsody project is easy! All you need is a few commands to create a containerized development environment running with the stack of your choice.

First, choose a development stack. To see all the available stacks, run:

`appsody list`{{execute}}

Create a new directory for your project and run appsody `init <stack>` to download the template project. We'll use the `nodejs-express` stack to create a fully functional Appsody project:

`mkdir -p ~/my-project
cd ~/my-project`{{execute}}

Initialize the stack:

`appsody init nodejs-express`{{execute}}

Wait until the image pull completes and then start the development container:

`appsody run --network host`{{execute}}

Great! Now the project is running in a docker container, and the container is linked to the project source code on your local system.

Keep the container running in the terminal and navigate to https://[[HOST_SUBDOMAIN]]-3000-[[KATACODA_HOST]].environments.katacoda.com/ to see the output. Leave the browser tab open for the following step.

**Note:** If you deployed Appsody on your own development machine, you would navigate to `https://localhost:3000` instead.
