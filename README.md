# dotnet-docker-example
Testing out building a .NET core container with docker

See [Microsoft's tutorial](https://dotnet.microsoft.com/learn/aspnet/microservice-tutorial/run-docker) for more information

## Running the app

#### Creating a docker image

```bash
docker build -t dotnet-docker-example .
```

* `docker build` builds an image from a `Dockerfile`
* `-t dotnet-docker-example` names this image `dotnet-docker-example`
* `.` is a filepath

#### After you have created the image

```bash
docker images
```
* You should see `dotnet-docker-example` in the list

#### To start the app

```bash
docker run -it --rm -p 3000:80 --name mycontainer dotnet-docker-example
```

* `docker run` tells docker to start a container based on a given image
* `-it` Keeps STDIN open, allocate pseudo TTY
* `--rm` Automatically remove the container when it exits
* `-p 3000:80` Binds port 3000 of the host machine to port 80 of the container
* `--name mycontainer` Names the container we are running
* `dotnet-docker-example` the name of the image from which we are building the container
