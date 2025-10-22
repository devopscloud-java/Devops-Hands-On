Docker Apache2 Container Setup
Objective

Save an existing Docker image (from Assignment 1).

Launch a container from this image mapping it to port 81.

Start the Apache2 service inside the container.

Verify accessibility via a web browser.

Steps
1. Save the image from Assignment 1

If your assignment 1 image is already built and named (for example assignment1-image), you can save it as a Docker image:

# Save the image locally (optional step if you want a tar file)
docker save -o assignment1-image.tar assignment1-image

2. Launch a container and map port 81
docker run -dit --name apache-container -p 81:80 assignment1-image


-dit: Run container in detached mode, interactive terminal.

--name apache-container: Name your container for easy reference.

-p 81:80: Map host port 81 to container port 80 (Apache default).

3. Access container and start Apache2
# Enter the container
docker exec -it apache-container /bin/bash

# Inside the container, start Apache2
service apache2 start

# (Optional) Check status
service apache2 status

4. Verify Apache2 in browser

Open a web browser and go to:

http://localhost:81


You should see the Apache2 default page (or your custom web page if added).

5. Additional commands (optional)
# To see running containers
docker ps

# To stop the container
docker stop apache-container

# To remove the container
docker rm apache-container

