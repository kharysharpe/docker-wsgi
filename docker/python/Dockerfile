############################################################
# Dockerfile to build Python WSGI Application Containers
# Based on Ubuntu
############################################################

# Set the base image to Ubuntu
FROM ubuntu:18.04

# File Author / Maintainer
LABEL maintainer="Khary Sharpe <ksharpe@email.com>"

# Add the application resources URL
RUN echo "deb http://archive.ubuntu.com/ubuntu/ $(lsb_release -sc) main universe" >> /etc/apt/sources.list

# Update the sources list
RUN apt-get update

# Install basic applications
RUN apt-get install -y tar git curl nano wget dialog net-tools build-essential

# Install Python and Basic Python Tools
RUN apt-get install -y python python-dev python-distribute python-pip

# Copy the application folder inside the container
ADD /webapp /webapp

# Get pip to download and install requirements:
RUN pip install -r /webapp/requirements.txt

# Expose ports
EXPOSE 80

COPY ./resources/server.py /webapp/server.py

# Set the default directory where CMD will execute
WORKDIR /webapp

# Set the default command to execute    
# when creating a new container
# i.e. using CherryPy to serve the application
CMD python server.py