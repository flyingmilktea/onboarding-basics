After using SSH connect to the server. Try to run hello world in Docker.

# Hello-World in Docker
[Hello-World image](https://hub.docker.com/_/hello-world)\
You can check out [Docker Hub](https://hub.docker.com/search?q=) for more Docker images.


Simply copy the following command to run hello world in Docker

```
docker run hello-world
```
If Docker unable to find the image locally, it will pull the image automatically

or you can pull the iamge manually
```
docker pull hello-world
docker run hello-world
```

Also you can specify the image by the tag
```
docker pull hello-world:latest
```

For more docker command you can checkout [docker doc](https://docs.docker.com/engine/reference/run/)