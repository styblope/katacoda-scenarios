# Installing Appsody

You can install Appsody on your system in a few easy steps by using our binary packages, which are available for macOS®, Ubuntu, Red Hat Enterprise Linux (RHEL), and Windows®.

**Note:** While you would normally install and use the Appsody CLI on your development machine, we'll instead use the provisioned Kubernetes cluster node throughout the exercise.

Download the latest install package from the [Appsody releases page](https://github.com/appsody/appsody/releases):

`wget https://github.com/appsody/appsody/releases/download/0.4.10/appsody_0.4.10_amd64.deb`{{execute}}

Install the package:

`sudo dpkg -i appsody_0.4.10_amd64.deb`{{execute}}
