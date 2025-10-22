Ubuntu Apache2 Docker Setup

This guide explains how to pull an Ubuntu Docker container, run it, install Apache2, and access the default Apache page via a browser.

Prerequisites

Docker installed on your system

Basic knowledge of terminal/command prompt

Steps
1. Pull the Ubuntu Container

Pull the latest Ubuntu image from Docker Hub:

docker pull ubuntu:latest

2. Run the Ubuntu Container and Map Port 80

Run the container and map the container's port 80 to the host's port 80:

docker run -it -d -p 80:80 --name my_ubuntu ubuntu:latest


-it : interactive terminal

-d : run container in detached mode

-p 80:80 : map host port 80 to container port 80

--name my_ubuntu : assign a name to the container

3. Install Apache2 Inside the Container

Access the container's shell:

docker exec -it my_ubuntu bash


Inside the container, update packages and install Apache2:

apt update
apt install apache2 -y


Start the Apache2 service:

service apache2 start


Verify Apache is running:

service apache2 status

4. Access the Apache Default Page

Open your browser and go to: http://localhost/

You should see the default Apache2 Ubuntu Default Page.

Optional: Stop and Remove the Container

To stop the container:

docker stop my_ubuntu


To remove the container:

docker rm my_ubuntu


✅ Task Completed: Ubuntu container with Apache2 running and accessible on port 80.
