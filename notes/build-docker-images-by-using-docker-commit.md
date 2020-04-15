Build Docker images by using Docker Commit 

docker run -it debian:jessie

ls

apt-get update && apt-get install -y git 


# Exit Then list running docker containers 

docker ps -a  

# Commit Changes 

docker commit <container-ID> <dockhubuser/container:imageTag>

e.g docker commit 988b8ftrb45b3b pmutua/debian:1.0

# To find the image 

docker images 

# Spin up the container based on new image you will enter into shell mode

docker run -it pmutua/debian:1.0

