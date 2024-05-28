# Use the official Ubuntu base image
FROM ubuntu:20.04

# Install essential packages
RUN apt-get update && apt-get install -y \
    python3-dev \
    python3-setuptools \
    python3-pip \
    python3-venv \
    mariadb-server \
    redis-server \
    curl \
    nodejs \
    npm

# Set up Node.js
RUN curl -sL https://deb.nodesource.com/setup_14.x | bash - && apt-get install -y nodejs && npm install -g yarn

# Install frappe-bench
RUN pip3 install frappe-bench

# Set up environment
RUN bench init --frappe-branch version-13 /workspace/frappe-bench
