Docker Assignments
Overview

This directory contains Docker assignments completed as part of [Devops/Docker]. The assignments focus on creating Docker containers, working with Docker images, and setting up services like Apache2 in Ubuntu containers.

Assignments
1. Ubuntu Container Setup

Tasks:

Pull an Ubuntu container.

Run the container and map port 80.

Install Apache2 inside the container.

Verify access to the Apache page from a browser.

2. Dockerfile Creation

Tasks:

Create a Dockerfile with Ubuntu base image.

Install Apache2 in the Dockerfile.

Ensure Apache2 runs automatically when the container starts.

3. Docker Image Save and Launch

Tasks:

Save the created image from Assignment 1.

Launch a container from the saved image and map it to port 81.

Start Apache2 service inside the container.

Verify Apache page access in a browser.

4. Replacing Default Apache Page

Tasks:

Create a sample HTML file.

Replace the default Apache index page inside the container with this sample HTML.

5. Docker Hub Upload

Tasks:

Use the saved Docker image from previous assignments.

Upload the image to Docker Hub.

Pull the image on a different machine and run it on port 80.

Start Apache2 service and verify the page.

Commands Used

Pull Ubuntu: docker pull ubuntu

Run container: docker run -it -p 80:80 ubuntu

Install Apache2: apt-get update && apt-get install apache2 -y

Build image: docker build -t <image_name> .

Save image: docker save -o <image_name>.tar <image_name>

Load image: docker load -i <image_name>.tar

Push image: docker push <username>/<image_name>

Pull image: docker pull <username>/<image_name>

Notes

Ensure Docker service is running before performing assignments.

Port mapping may be adjusted according to system availability.

Always verify container status using docker ps
