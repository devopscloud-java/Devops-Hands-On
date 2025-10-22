Task: Replace default Apache page with a sample HTML using Docker
1. Create a sample HTML file

Create a file named index.html in your project directory with content like:

<!DOCTYPE html>
<html>
<head>
    <title>My Sample Page</title>
</head>
<body>
    <h1>Welcome to My Sample Docker Apache Page!</h1>
    <p>This page is served from a Docker container.</p>
</body>
</html>

2. Dockerfile (based on previous task)

If your previous Dockerfile installs Apache on Ubuntu, modify it to include the sample HTML:

# Use Ubuntu as base image
FROM ubuntu:latest

# Install Apache2
RUN apt-get update && \
    apt-get install -y apache2 && \
    apt-get clean

# Copy sample HTML file into the Apache default web folder
COPY index.html /var/www/html/index.html

# Expose port 80
EXPOSE 80

# Start Apache in the foreground
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]


Explanation:

COPY index.html /var/www/html/index.html replaces the default Apache page.

CMD ensures Apache runs when the container starts.

3. Build and run the Docker container
# Build Docker image
docker build -t my-apache-sample .

# Run Docker container mapping port 80
docker run -d -p 80:80 my-apache-sample

4. Verify

Open your browser and go to http://localhost/ (or your Docker host IP).

You should see your sample HTML page instead of the default Apache page.

README Sample Content
# Docker Apache HTML Replacement

## Task
Replace the default Apache web page with a custom sample HTML page using Docker.

## Steps Performed
1. Created `index.html` as a sample HTML page.
2. Modified Dockerfile to copy `index.html` to `/var/www/html/index.html`.
3. Built and ran Docker container exposing port 80.
4. Verified custom page loads correctly in browser.

## Commands Used
docker build -t my-apache-sample .
docker run -d -p 80:80 my-apache-sample
