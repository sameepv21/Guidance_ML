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

## Miscellenious
* Please Refer to [this site](https://docs.docker.com/get-started/overview/#the-docker-daemon) for some technical terms