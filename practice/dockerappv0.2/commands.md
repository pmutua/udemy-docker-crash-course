docker ps 

docker run -d --name redis redis:3.2.0

docker build -t dockerapp:v0.3 .

docker run -d -p 5000:5000 --link redis dockerapp:v0.3

# Inspect container 

docker inspect bb0945444cd343 | grep IP 

