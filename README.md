# Docker Build, Push, Continuous Integration (CI), Continuous Deployment (CD) and Versioning for a Node JS application

![AyeAye](https://github.com/devops-recipes/push-docker-hub/blob/master/public/resources/images/captain.png)

A simple Node JS application with unit tests and coverage reports using mocha 
and istanbul. This repo demonstrates a release job that versions the Node JS application after it is deployed to an ECS cluster.


## Run CI for this repo on Shippable
* Fork this repo into your local repo
* Login into the [Continuous Integration Service](wwww.shippable.com) 
* Create an [integration](http://docs.shippable.com/integrations/imageRegistries/dockerHub/) on shippable to your docker hub
* All CI configuration is in `shippable.yml`
* Follow these [CI Setup Instructions](http://docs.shippable.com/ci/runFirstBuild/) if you have never used Shippable CI Service
* Update the integrationName in the integration.hub section if you used something other than `shipDH`
* Change the DOCKER_REPO and DOCKER_ACC to point to your repo and docker account
* You should be able to run a manual build or webhook build on commit

## Add Continuous Delivery pipelines to deploy to Amazon ECS
* Fork this repo into your local repo
* Follow instructions to [connect your Continuous Integration project to your Continuous Delivery pipelines](http://docs.shippable.com/tutorials/pipelines/connectingCiPipelines/).
* Create an [integration](http://docs.shippable.com/integrations/containerServices/ecs/) for Amazon ECS
* All pipeline config is in shippable.resources.yml and shippable.jobs.yml. Check these files and update config wherever the comment asks you to replace with your specific values
* This demo uses a declarative job type called 'deploy' in Shippable to deploy to ECS.
* This demo uses a declarative job type called 'release' to version the deployment to ECS.

## CD Reports on Shippable

### CD Pipeline View

### CD Deployment Job Console Output

### CD Release Job Console Output

## CI Reports on Shippable

### CI Integration View

### CI Console Output
