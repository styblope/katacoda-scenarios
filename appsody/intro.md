# Welcome to Appsody

[Appsody](https://appsody.dev) is designed to help you develop containerized applications for the cloud.

If you're a software developer, our aim is to greatly improve your developer experience by removing the burden of managing the full software development stack. With Appsody,
you can build applications for the cloud that are ready to be deployed to Kubernetes without being an expert on the underlying container technology. You can simply focus on the important stuff - developing application code!

Appsody consists of 3 key components:

**Appsody Stacks**

These are configurable technology stacks built with popular runtimes and frameworks, such as *Java with Eclipse MicroProfile* and *Node.js with Express*. These stacks  provide the foundation for building applications that can be deployed and managed effectively in Kubernetes. Stacks allow for rapid development, whilst giving the stack provider the ability to control how the applications are composed. For example, which security policies are applied or which version of a dependency is used. For more
information, see [Appsody Stacks](https://appsody.dev/docs/stacks/stacks-overview).

**Appsody Hub**

The Hub is the central point of control for Appsody Stacks where you can find available stacks, create new stacks, or modify existing ones. You can use the Hub content in the public repo or clone it to provide a private Hub that's based on your requirements. By making changes to the Stacks in the Hub, you can deploy updates to any application that's been built on them, simply by restarting the application.

**Appsody CLI**

No project is complete without a nice new CLI to play with. The [Appsody CLI](https://appsody.dev/docs/using-appsody/cli-commands) is powerful and intuitive, allowing developers to discover the available stacks and bring them into their local development environment. From here, they can build, run, test, and deploy applications locally. The Docker container that's built for an application can then be integrated with Tekton pipelines and deployed to Kubernetes cloud environments. For more information, see [Deploying your app through a Tekton pipeline](https://appsody.dev/docs/using-appsody/building-and-deploying#Deploying-your-app-through-a-Tekton-pipeline).

## How does it work?

Appsody provides pre-configured application stacks, which use the well-known Dockerfile syntax to specify which language runtimes, frameworks, libraries, and tools are included. Project templates build upon these stacks, providing developers with a templatized application to bring into their IDE of choice and begin development.

When developers run, debug, or test their application using the Appsody CLI, it starts a container with the stack image, makes the development workspace available to the running container, and starts the Appsody controller. The controller is configurable through environment variables in the stack and manages the application within the running container. For example, the controller can watch for changes in the application `/src` directory. When these changes are saved, the controller restarts the application running in a docker container.

<p align="center">
<img src="https://raw.githubusercontent.com/appsody/website/master/content/docs/images/appsody_flow.png" alt="" style="width:800px">
</p>

## Contributing

We welcome all contributions.

If you'd like to get involved, read our [Contribution guidelines](https://github.com/appsody/website/blob/master/CONTRIBUTING.md) and come and chat to us in [Slack](https://appsody-slack.eu-gb.mybluemix.net/).

Want to see your framework available as an Appsody Stack? See [Creating](https://appsody.dev/docs/stacks/create) and [Modifying](https://appsody.dev/docs/stacks/modify) Stacks and join the `#stack-providers` channel on Slack to introduce yourself!

