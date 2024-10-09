# Nginx-Server-Term-Project

# Create Nginx Directory 
Mkdir nginx – container
CD nginx - container

# Create Docker File
touch Dockerfile

# Open Dockerfile
nano Docker

# Add Text to Nano:
# Use the official Ubuntu as a parent image
FROM ubuntu:latest
# Set environment variables to prevent interactive prompts during      installation
ENV DEBIAN_FRONTEND=noninteractive
# Update the package list and install Nginx
RUN apt-get update && \
    apt-get install -y nginx && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
# Expose port 80 to the outside world
EXPOSE 80
# Start Nginx in the foreground
CMD ["nginx", "-g", "daemon off;"]

# Exit out of nano
Control x, type yes and hit enter

# Build the image
docker build -t my-nginx-container .

# Run the Container
docker run -p 80:80 --name my-nginx-container my-nginx-container

# Verify if Port is Running on web
type localhost

# To Stop Container
docker stop my-nginx-container

# Check if Container is Still Running
docker ps






