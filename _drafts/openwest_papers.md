## Docker a day keeps the package managers away

Is Docker all the things it's hyped up to be? Have you been wondering what all the hype is about? Perhaps you don't even know what Docker really is. Come discover why Docker is the best thing to happen since sliced bread. Take an adventure through the history of DevOps to discover why Docker was created, what problems it solves, and where devops will be in the near future. 

**Full Description:**

This presentation will walk through a history of major devops changes such as Package Management, Configuration Managers (such as Chef), VMs, containers, and Docker. In the presentation, we will discuss about each one, how they changed the game, and the downsides of them all. Learn why containers are so great from a devops point of view. We will talk about the problems containers aim to solve as well as why Docker was created and what it adds to the container world. We will also talk about rkt and the Open Container Initiative and what this means for the future.

## It works fine for me!

Docker aims to solve the "but it works for me" phenomenon by containerizing all of your code. In this hands-on tutorial we will walk through Docker tools such as docker, docker-compose, and docker-machine to show you how Docker can empower your team. 

**Full Description:**

This is a beginner's guide to Docker intended for developers. We will walk through an example of creating two applications, one in Python and another in Java. For each we will containerize the code using official Docker containers. The two applications will then talk to each other. Finally, docker-compose will be used to show how the two can talk to each other in a development environment, as well as a production environment.


## Less is more for Docker layers

Is your Docker honeymoon over? Have you realized how annoying it is to download hundreds of megabytes for small changes? Learn how Docker layers work and how to minimize each layer in your container. Shrink a 300MB container to about 8MB.

**Full Description:**

Multiple methods for minimizing containers will be mentioned. 
* Docker layering 
  * Examples used to show that a layer isn't always what you would expect
  * Common gotchas such as when you remove files, you are actually making the container larger
  * Improved layering techniques
  * When are layers good, and when they're bad
* Alpine Linux, a small linux distro with a package manager and how 
  * building things from Alpine can reduce your container drastically
* Other minimization techniques
  * layer squashing
  * skinnywhatle
  * scratch image

## Introduction to rkt

No tagline yet.

**Full Description:**

An intro to rkt. Walk through how to build a container using rkt. 
* Running rkt containers
* How to build your own
* How to deploy
* How to store
* How to distribute
* Running Docker containers from rkt
* quay.io, a repository for rkt
* rkt vs. Docker

## Moving to Microservices with Docker

Come watch as Nick explains the journey Canopy had to take to move from monolith to microservices. Learn how Docker can help you with the journey and the pains that you will see along the way.

**Full Description:**

We will talk about how Canopy used Docker to move us to microservices and the journey we took. 

1. Dockerize all the things
1. Split up the repos
1. Pipelining - Independent deploys
1. Stabbed in the Backwards Compatilbility
1. DevOps training began
1. Add new services
1. Not enough environments
1. Docker-compose to the rescue
1. Ok docker-compose is too much
1. Shadow-prod
1. Feature Toggles

-- notes for myself on moving to microservices (aka not part of my submission)--
At first we tried to dockerize everything. This was intially just a container around the monolith. Then we had to split repositories into two, frontend, and backend, then create a container for each. Next, a deployment pipeline was created for each so that they could be deployed independently. Then we struggled with backwards compatibility and had to train everyone. Once things were working, we then added a new service in Java. We used docker-compose to allow everyone to run all the services in their development environment without needing to worry about the services they don't touch. As we added more and more services, this got out of hand, and there were too many services in the docker-compose files, and too many files to update if you wanted to change your service configuration. Docker didn't completely offer the "add it and forget about it" that we had hoped for. To fix this we created a "prod-like" environment, so that you could point your dev environment to a prod-like environment for the services you are not directly interacting with.
Also, we had a single prod and stage environment, but that created a bottleneck so we had to create multiple integration environments. Lastly we moved away from feature branches to feature toggles using a feature toggle service.
