Steps to Perform the Tasks
1. Use the saved image from the previous assignment

Assuming in your previous assignment you saved an image as my-apache-image:

docker images
# Verify your image exists

2. Upload the image to Docker Hub

Login to Docker Hub:

docker login


Enter your Docker Hub username and password.

Tag your image for Docker Hub:

docker tag my-apache-image yourdockerhubusername/my-apache-image:latest


Push the image to Docker Hub:

docker push yourdockerhubusername/my-apache-image:latest


Replace yourdockerhubusername with your actual Docker Hub username.

3. Pull the image on a separate machine and launch it on port 80

Pull the image from Docker Hub:

docker pull yourdockerhubusername/my-apache-image:latest


Run the container and map port 80:

docker run -d -p 80:80 --name apache-container yourdockerhubusername/my-apache-image:latest

4. Start the Apache2 service inside the container
docker exec -it apache-container bash
# Inside the container
service apache2 start
exit

5. Verify Apache2 service

Open a browser on the separate machine.

Go to: http://<machine-ip>
You should see the Apache2 default page.

Sample README File
# Docker Apache2 Deployment

## Description
This project demonstrates deploying an Apache2 service using Docker. The workflow includes creating a Docker image, uploading it to Docker Hub, and running it on a separate machine.

## Steps Performed
1. Used the saved Docker image from the previous assignment.
2. Tagged and uploaded the image to Docker Hub.
3. Pulled the image on a separate machine.
4. Launched the container on port 80.
5. Started the Apache2 service inside the container.
6. Verified the Apache2 service by accessing it via a web browser.

## Docker Commands Used
```bash
docker login
docker tag my-apache-image yourdockerhubusername/my-apache-image:latest
docker push yourdockerhubusername/my-apache-image:latest
docker pull yourdockerhubusername/my-apache-image:latest
docker run -d -p 80:80 --name apache-container yourdockerhubusername/my-apache-image:latest
docker exec -it apache-container bash
service apache2 start
exit

Verification
Access http://<machine-ip> in a web browser to verify the Apache2 page is visible.

Access http://<machine-ip> in
