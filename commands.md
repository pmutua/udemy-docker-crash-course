
# List all containers (only IDs)

`docker ps -aq`

# Stop all running containers

`docker stop $(docker ps -aq)`


# Remove all containers

`docker rm $(docker ps -aq)`

# Remove all images

`docker rmi $(docker images -q)`

# Rebuild image 

docker build -t pmutua/debian .

# Start continer 

docker run cbvfvswu57533

# Overide CMD command at run time

docker run cbvfvswu57533 echo "hello world"

# Push Images 

- Step 1 - Find Images 

    `docker images`

- Step 2 - rename tag 

docker tag bc4332323253 jleetutorial /debian:1.01

- Step 3 - Login docker 

 docker login --username=pmutua 

- Step 4 - push container to repository 

docker push jleetutorial/debian:1.01

Note:

- Docker will use the latest as default tag when no tag provided.