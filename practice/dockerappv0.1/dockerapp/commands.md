# Find Images 

docker images 

# Build container 

docker build -t dockerapp:v0.1 .

# Run container in background 

docker run -d -p 5000:5000 <imageID>

# Check IP of docker machine 

docker-machine ls 

# Get inside the container 

docker exec -ti <containerID> bash

# Check your current directory 

pwd 

# Go to home directory 

cd /home/admin/

# Check running processes in the container 

ps axu 