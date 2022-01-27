# What is Docker?
* Platform for developing, shipping and running applications.
* Enables you to separate your application with your infrastrucutre for quicker software delivery.
* Provides ability to package and run an application in a loosely isolated environment called a container.
* Containers are lightweight and contain everything needed to run the application.
* They can even be executed simultaneously on the same host.

# Layman's Terms
* Suppose you are developing on Ubuntu 20.04 OS.
* Your server is running on CentOS.
* This makes it difficult for your application to run because there is a possibility that the packages required by your application are not available in CentOS.
* This creates the need for docker.
* Docker, itself is a full fledged platform independent replica of your application.
* This means that you can run your application in any environment without worrying about the technicalities associated with it.
* This helps your code to reach production faster than the conventional methods.

# Uses
* Provides Standardized Environment
* Provides CI/CD Functionality
* Responsive deployment and scaling

# Advantages
* Lightweight and Fast
* Convenient
* Responsive deployment
* Scalable

# Architecture
* Client-server (Client is docker client/compose and server is docker daemon).
* Communication between then is done using REST API.
* Uses UNIX sockets.
* Written in Go Programming language.
* Note that docker client is for single container whereas docker compose is for a set of containers.
* Daemon listens for docker api requests and manages docker objects such as images, containers, networks and volumes.
* Daemon can also communicate with other daemons to manage docker services.
* Docker client can comminicate with more than one docker daemon.

# Installation on Ubuntu
* Note that we are using installation through repository method.
* Hence before installing docker, we need to set up a docker repository.
* Steps
    * Set up required packages
    ```bash
    sudo apt-get update

    sudo apt-get install \
        ca-certificates \
        curl \
        gnupg \
        lsb-release
    ```
    * Add doker's official GPG key
    ```bash
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
    ```
    * Set up a stable repo
    ```bash
    echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    ```
    * Install docker engine
    ```bash
    sudo apt-get update
    sudo apt-get install docker-ce docker-ce-cli containerd.io
    ```
    * Verify whether docker is installed or not
    ```bash
    sudo docker run hello-world
    ```

# Terminologies
* Container
    * Container is a sandboxed process on your machine that is isolated from all other processes on the host machine.
    * It is a runnable instance of an image.
    * Can be run on local machines, virtual machines or be deployed to the cloud.
    * Can be run on any OS.
    * Each container is isolated from other and run their own software, binaries and configurations.
* Image
    * Container uses an isolated filesystem.
    * This custom filesystem is provided by a container image.
    * It contains everything needed to run an application including all dependencies, configuarations, scripts, bins, env variables etc.
* Dockerfile
    * Used to build the application.
    * It is a text-based script of instructions that is used to create a container image.
* Docker Registry
    * It is analogous to github repository.
    * But instead of github it is docker hub.

# Commands
* docker run <OPTIONS> <IMAGE_NAME>
    * options can be viewed in the documentation
* docker build <OPTIONS> <PATH_OF_CONTAINER>
    * downloads, installsand builds a lot of layers
* docker stop <CONTAINER_ID>
    * stops a running docker container with id = CONTAINER_ID
* docker container ls
    * dispkays all running docker containers.
    * "docker ps" returns the same thing as the above command.
* docker rm <CONTAINER_ID>
    * Removes the container from your system.
    * Stop only kills the docker process for that container id but rm removes the entire container with that particular container id.
    * Stop and remove in a single line.
        * docker rm -f <CONTAINER_ID>
* docker push <USERNAME>/<REPO_NAME>
    * Pushes the changes to docker registry.
* docker image ls
    * Same like docker container ls but with image.
* docker login -u <USERNAME>
    * Log in to docker account in your local machine/system.
* docker tag <IMAGE_NAME> <USERNAME>/<REPO_NAME>

## Miscellenious
* Please Refer to [this site](https://docs.docker.com/get-started/overview/#the-docker-daemon) for some technical terms