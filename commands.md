
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
