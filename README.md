# Docker Interview Questions and Answers from [FullStack.Cafe](https://www.fullstack.cafe)

> You could also find all the answers here 👉 https://www.fullstack.cafe/Docker.

<p align="center">
  <a href="https://www.fullstack.cafe">
  <img src="https://user-images.githubusercontent.com/13550565/73042643-e53caa80-3e9c-11ea-9019-f70c2158c249.png">
  </a>
</p>

## Q1: What is Docker? ⭐

**Answer:**

* Docker is a containerization platform which packages your application and all its dependencies together in the form of containers so as to ensure that your application works seamlessly in any environment be it development or test or production.
* Docker containers, wrap a piece of software in a complete filesystem that contains everything needed to run: code, runtime, system tools, system libraries etc. anything that can be installed on a server.
* This guarantees that the software will always run the same, regardless of its environment.

🔗 **Source:** [edureka.co](https://www.edureka.co/blog/interview-questions/docker-interview-questions/)


## Q2: How to build envrionment-agnostic systems with Docker? ⭐⭐

**Answer:**

There are three main features helping to achieve that:

*   Volumes
*   Environment variable injection
*   Read-only file systems

🔗 **Source:** [rafalgolarz.com](http://rafalgolarz.com/blog/2017/03/11/docker_interview/)


## Q3: Can you remove (‘docker rm’) a container that is paused? ⭐⭐

**Answer:**

No, to remove a container it must be stopped first.

🔗 **Source:** [rafalgolarz.com](http://rafalgolarz.com/blog/2017/03/11/docker_interview/)


## Q4: When would you use ‘docker kill’ or ‘docker rm -f’? ⭐⭐

**Answer:**

If you must stop the container really quickly… (someone pushed something to production on Friday evening?… ;) )

🔗 **Source:** [rafalgolarz.com](http://rafalgolarz.com/blog/2017/03/11/docker_interview/)


## Q5:  How to link containers? ⭐⭐

**Answer:**

The simplest way is to use network port mapping. There’s also the **\- -link** flag which is deprecated.

🔗 **Source:** [rafalgolarz.com](http://rafalgolarz.com/blog/2017/03/11/docker_interview/)


## Q6: What is the difference between a Docker image and a container? ⭐⭐

**Answer:**

An instance of an image is called a container. You have an image, which is a set of layers. If you start this image, you have a running container of this image. You can have many running containers of the same image.

You can see all your images with `docker images` whereas you can see your running containers with `docker ps` (and you can see all containers with `docker ps -a`).

So a running instance of an image is a container.

🔗 **Source:** [stackoverflow.com](https://stackoverflow.com/questions/23735149/what-is-the-difference-between-a-docker-image-and-a-container/23736802#23736802)


## Q7: What is the difference between the `COPY` and `ADD` commands in a Dockerfile? ⭐⭐

**Answer:**

Although `ADD` and `COPY` are functionally similar, generally speaking, `COPY` is preferred. 

That’s because it’s more transparent than ADD. COPY only supports the basic copying of local files into the container, while ADD has some features (like local-only tar extraction and remote URL support) that are not immediately obvious. Consequently, the best use for ADD is local tar file auto-extraction into the image, as in ADD rootfs.tar.xz /.

🔗 **Source:** [stackoverflow.com](https://stackoverflow.com/questions/16647069/should-i-use-vagrant-or-docker-for-creating-an-isolated-environment)


## Q8: What is the difference between CMD and ENTRYPOINT in a Dockerfile? ⭐⭐

**Answer:**

Both `CMD` and `ENTRYPOINT` instructions define what command gets executed when running a container. There are few rules that describe their co-operation.
 
1. Dockerfile should specify at least one of `CMD` or `ENTRYPOINT` commands.
2. `ENTRYPOINT` should be defined when using the container as an executable.
3. `CMD` should be used as a way of defining default arguments for an `ENTRYPOINT` command or for executing an ad-hoc command in a container.
4. `CMD` will be overridden when running the container with alternative argumen

🔗 **Source:** [stackoverflow.com](https://stackoverflow.com/questions/21553353/what-is-the-difference-between-cmd-and-entrypoint-in-a-dockerfile)


## Q9: How do I transfer a Docker image from one machine to another one without using a repository, no matter private or public? ⭐⭐

**Answer:**

You will need to save the Docker image as a tar file:

```sh
docker save - o <path for generated tar file> <image name>
```

Then copy your image to a new system with regular file transfer tools such as `cp` or `scp`. After that you will have to load the image into Docker:

```sh
docker load -i <path to image tar file>
```

🔗 **Source:** [stackoverflow.com](https://stackoverflow.com/questions/23935141/how-to-copy-docker-images-from-one-host-to-another-without-using-a-repository/23938978#23938978)


## Q10: What is Docker image? ⭐⭐

**Answer:**

**Docker image** is the source of Docker container. In other words, Docker images are used to create containers. Images are created with the build command, and they’ll produce a container when started with run. Images are stored in a Docker registry such as ` registry.hub.docker.com` because they can become quite large, images are designed to be composed of layers of other images, allowing a minimal amount of data to be sent when transferring images over the network.

🔗 **Source:** [edureka.co](https://www.edureka.co/blog/interview-questions/docker-interview-questions/)


## Q11: What is Docker container? ⭐⭐

**Answer:**

**Docker containers** include the application and all of its dependencies, but share the kernel with other containers, running as isolated processes in user space on the host operating system. Docker containers are not tied to any specific infrastructure: they run on any computer, on any infrastructure, and in any cloud.

🔗 **Source:** [edureka.co](https://www.edureka.co/blog/interview-questions/docker-interview-questions/)


## Q12: What is Docker hub? ⭐⭐

**Answer:**

**Docker hub** is a cloud-based registry service which allows you to link to code repositories, build your images and test them, stores manually pushed images, and links to Docker cloud so you can deploy images to your hosts. It provides a centralized resource for container image discovery, distribution and change management, user and team collaboration, and workflow automation throughout the development pipeline.

🔗 **Source:** [edureka.co](https://www.edureka.co/blog/interview-questions/docker-interview-questions/)


## Q13: Do I lose my data when the Docker container exits? ⭐⭐

**Answer:**

There is no loss of data when any of your Docker containers exits as any of the data that your application writes to the disk in order to preserve it. This will be done until the container is explicitly deleted. The file system for the Docker container persists even after the Docker container is halted.

🔗 **Source:** [mindmajix.com](https://mindmajix.com/docker-interview-questions)


## Q14: What are the various states that a Docker container can be in at any given point in time? ⭐⭐

**Answer:**

There are four states that a Docker container can be in, at any given point in time. Those states are as given as follows:

* Running
* Paused
* Restarting
* Exited

🔗 **Source:** [mindmajix.com](https://mindmajix.com/docker-interview-questions)


## Q15: Is there a way to identify the status of a Docker container? ⭐⭐

**Answer:**

We can identify the status of a Docker container by running the command 

```sh
docker ps –a
```

which will in turn list down all the available docker containers with its corresponding statuses on the host. From there we can easily identify the container of interest to check its status correspondingly.

🔗 **Source:** [mindmajix.com](https://mindmajix.com/docker-interview-questions)


## Q16: What is Build Cache in Docker? ⭐⭐

**Answer:**

When we build an Image, Docker will process each line in Dockerfile. It will execute the commands on each line in the order that is mentioned in the file. But at each line, before running any command, Docker will check if there is already an existing image in its cache that can be reused rather than creating a new image.

🔗 **Source:** [mindmajix.com](https://mindmajix.com/docker-interview-questions)


## Q17: What are the most common instructions in Dockerfile? ⭐⭐

**Answer:**


Some of the common instructions in Dockerfile are as follows:
*   **FROM**: We use FROM to set the base image for subsequent instructions. In every valid Dockerfile, FROM is the first instruction.
*   **LABEL**: We use LABEL to organize our images as per project, module, licensing etc. We can also use LABEL to help in automation.  
    In LABEL we specify a key value pair that can be later used for programmatically handling the Dockerfile.
*   **RUN**: We use RUN command to execute any instructions in a new layer on top of the current image. With each RUN command we add something on top of the image and use it in subsequent steps in Dockerfile.
*   **CMD**: We use CMD command to provide default values of an executing container. In a Dockerfile, if we include multiple CMD commands, then only the last instruction is used.

🔗 **Source:** [knowledgepowerhouse.com](https://www.knowledgepowerhouse.com/what-are-the-most-common-instructions-in-dockerfile/1224)


## Q18: What type of applications - Stateless or Stateful are more suitable for Docker Container? ⭐⭐

**Answer:**

It is preferable to create Stateless application for Docker Container. We can create a container out of our application and take out the configurable state parameters from application. Now we can run same container in Production as well as QA environments with different parameters. This helps in reusing the same Image in different scenarios. Also a stateless application is much easier to scale with Docker Containers than a stateful application.

🔗 **Source:** [mindmajix.com](https://www.knowledgepowerhouse.com/what-type-of-applications-stateless-or-stateful-are-more-suitable-for-docker-container/1208)


## Q19: What is the difference between ‘docker run’ and ‘docker create’? ⭐⭐

**Answer:**

The primary difference is that using **‘docker create’** creates a container in a stopped state.

**Bonus point:** You can use **‘docker create’** and store an outputed container ID for later use. The best way to do it is to use **‘docker run’** with -**\-cidfile FILE\_NAME** as running it again won’t allow to overwrite the file. A good practice is to keep well ogranised directory structure: /containers/web/server1/ws.cid containers/web/server3/ws.cid

🔗 **Source:** [rafalgolarz.com](http://rafalgolarz.com/blog/2017/03/11/docker_interview/)


## Q20: What’s the difference between a repository and a registry? ⭐⭐

**Answer:**

* **Docker registry** is a service for hosting and distributing images (the default one is the Docker Hub). 
* **Docker repository** is a collection of related Docker images (the same name but with different tags).

🔗 **Source:** [rafalgolarz.com](http://rafalgolarz.com/blog/2017/03/11/docker_interview/)


## Q21: What is the default CPU limit set for a container? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q22: Can you create containers wihout their own PID namespace? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q23: Explain basic Docker usage workflow ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q24: What is the difference between Docker Image and Layer? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q25: What is virtualisation? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q26: What is Hypervisor? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q27: Could you explain what is Emulation? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q28: Should I use Vagrant or Docker for creating an isolated environment? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q29: What is the difference between CMD and ENTRYPOINT in a Dockerfile? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q30: What is the difference between “expose” and “publish” in Docker? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q31: Docker Compose vs. Dockerfile - which is better? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q32: What is Docker Swarm? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q33: What is the preferred way of removing containers - ‘docker rm -f’ or ‘docker stop’ then followed by a ‘docker rm’? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q34: What exactly do you mean by “Dockerized node”? Can this node be on-premises or in the cloud? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q35: How can we control the startup order of services in Docker compose? ⭐⭐⭐

**Questions Details:**

I have a container which depends on a redis databse container. However, it takes longer for redis to load in memory which causes the first container to exit. I was wondering if there is a better alternative as I would try to avoid the wait for it script?


 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q36: How will you monitor Docker in production? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q37: What is the purpose of EXPOSE command in Dockerfile? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q38: What happens if you add more than one CMD instruction to a Dockerfile? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q39: When you limit the memory for a container, does it reserve (guarantee) the memory? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q40: What is an orphant volume and how to remove it? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q41: How virtualization works at low level? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q42: What is Paravirtualization? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q43: How is Docker different from a virtual machine? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q44: Is it possible to generate a Dockerfile from an image? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q45: Can you explain dockerfile ONBUILD instruction? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q46: What are the different kinds of namespaces available in a Container? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q47: Is it good practice to run stateful applications on Docker? What are the scenarios where Docker best fits in? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q48: What is the difference between Docker RUN, CMD and ENTRYPOINT? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q49: Can you run Docker containers natively on Windows? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q50: Why did Docker jump from version 1.13 to 17.03? ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q51: How does Docker run containers in non-Linux systems? ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q52: How containers works at low level? ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q53: Name some limitations of containers vs VM ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q54: How to use Docker with multiple environments? ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**


## Q55: Why Docker compose does not wait for a container to be ready before moving on to start next service in dependency order? ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Docker)**



