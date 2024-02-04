# Use Ubuntu 22.04 as base image
FROM ubuntu:22.04

# Set environment variables to avoid interactive dialog during installation
ENV DEBIAN_FRONTEND=noninteractive

# Update the package repository and install packages
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    python3 \
    python3-pip \
    python3-venv \
    git \
    git-extras && \
    # Clean up
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Create a new user 'ubuntu'
RUN useradd -m ubuntu

# Switch to the new user
USER ubuntu

# Set the working directory
WORKDIR /home/ubuntu

# Copy your Flask app to the container
COPY --chown=ubuntu:ubuntu . /home/ubuntu/app

# Install Python dependencies globally
RUN python3 -m pip install -r /home/ubuntu/app/requirements.txt

# Set the environment variable for Flask
ENV FLASK_APP=/home/ubuntu/app/app.py
ENV PATH="/home/ubuntu/.local/bin:${PATH}"

# Expose the port your app runs on
EXPOSE 5000

# Set the working directory to your app directory
WORKDIR /home/ubuntu/app

# Set the default command to run your app
CMD ["flask", "run", "--host=0.0.0.0"]
