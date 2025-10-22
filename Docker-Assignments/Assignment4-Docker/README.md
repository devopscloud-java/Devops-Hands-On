Dockerfile:

# Use Ubuntu as the base image
FROM ubuntu:latest

# Prevent interactive prompts during package installation
ENV DEBIAN_FRONTEND=noninteractive

# Update package list and install Apache2
RUN apt-get update && \
    apt-get install -y apache2 && \
    apt-get clean

# Expose port 80 to access Apache
EXPOSE 80

# Start Apache2 in the foreground when the container runs
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]


Explanation of steps:

FROM ubuntu:latest → Sets Ubuntu as the base image.

ENV DEBIAN_FRONTEND=noninteractive → Avoids prompts during apt-get installs.

RUN apt-get update && apt-get install -y apache2 && apt-get clean → Updates packages, installs Apache2, and cleans cache.

EXPOSE 80 → Opens port 80 for HTTP traffic.

CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"] → Runs Apache2 in the foreground so the container stays alive.
