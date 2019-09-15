FROM ubuntu:19.04

# File Author / Maintainer
LABEL maintainer="Khary Sharpe <ksharpe@email.com>"

# Add the application resources URL
# RUN echo "deb http://archive.ubuntu.com/ubuntu/ $(lsb_release -sc) main universe" >> /etc/apt/sources.list

# Update the sources list
RUN apt-get update

# Install basic applications
RUN apt-get install -y tar git curl nano wget dialog net-tools build-essential

# Install Python and Basic Python Tools
RUN apt-get install -y python python-dev python-distribute python-pip libssl-dev

# Get pip to download and install requirements:
RUN pip install -r /webapp/current/requirements.txt

# Expose ports
EXPOSE 80

COPY ./resources/server.py /webapp/current/server.py

# Set the default directory where CMD will execute
WORKDIR /webapp/current

# Set the default command to execute    
# when creating a new container
# i.e. using CherryPy to serve the application
CMD python server.py