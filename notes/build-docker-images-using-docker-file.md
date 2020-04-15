# Build image from docker file

docker build -t <dockerhubusername/imagename:tag> <docker-build-context-path>

e.g `docker build -t pmutua/debian:1.0  . `

Note:

Images are persistent and readonly