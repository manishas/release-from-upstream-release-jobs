# Docker Continuous Deployment (CD) and Versioning of Java and Node docker images.

![AyeAye](https://github.com/devops-recipes/push-docker-hub/blob/master/public/resources/images/captain.png)

This project implements a pipeline that versions and continuously deploys java and node docker images to an ECS cluster. It leverages 
docker images built by -

- [Node tutorial](https://github.com/devops-recipes/release-single-component) that builds a node docker image and pushes the image to Docker hub.
- [Java tutorial](https://github.com/devops-recipes/ci-java-push-ecr) that builds a java war docker image and pushes the image to EC2 Container Registry.


## Add Continuous Delivery pipelines to deploy to Amazon ECS
* Fork this repo into your local repo
* Follow instructions to [connect your Continuous Integration project to your Continuous Delivery pipelines](http://docs.shippable.com/tutorials/pipelines/connectingCiPipelines/).
* Create an [integration](http://docs.shippable.com/integrations/containerServices/ecs/) for Amazon ECS and docker hub.
* All pipeline config is in shippable.resources.yml and shippable.jobs.yml. Check these files and update config wherever the comment asks you to replace with your specific values
* This demo uses a declarative job type called 'deploy' in Shippable to deploy to ECS.
* This demo uses a declarative job type called 'release' to version the deployment to ECS.

## CD Reports on Shippable

### Integration View
![Integration View](https://github.com/devops-recipes/release-single-component/blob/master/public/resources/images/integration-view.png)

### CD Pipeline View
![CD Pipeline View](https://github.com/devops-recipes/release-single-component/blob/master/public/resources/images/pipeline-view.png)

### CD Release Job Console Output
![CD Release Job Console Output](https://github.com/devops-recipes/release-single-component/blob/master/public/resources/images/release-job-output.png)

### CD Deployment Job Console Output
![CD Deployment Job Console Output](https://github.com/devops-recipes/release-single-component/blob/master/public/resources/images/deploy-job-output.png)
