# Set the base image to Ubuntu
FROM redis

# File Author / Maintainer
MAINTAINER Kevin Murillo Fernández

# Update the repository and install Redis Server
RUN apt-get update && apt-get install -y redis-server

# Expose Redis port 6379
EXPOSE 6379