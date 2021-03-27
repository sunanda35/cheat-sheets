# **Docker-CLI cheat sheet**

# Run a new Container---------

**Start a new container from an image:**
- `docker run IMAGE`
- `docker run nginx`

....assign it a name:
- `docker run --name CONATAINER IMAGE`
- `docker run --name web nginx`

....map this port:
- `docker run -p HOSTPORT:CONTAINERPORT IMAGE`
- `docker run -p 8080:80 nginx`

....map all ports:
- `docker run -P IMAGE`
- `docker run -P nginx`

....start container in background:
- `docker run -d IMAGE`
- `docker run -d nginx`

....assign it a hostname:
- `docker run --hostname HOSTNAME IMAGE`
- `docker run --hostname srv nginx`

....add a dns entry:
- `docker run --add-host HOSTNAME:IP IMAGE`

....map a local directory into the container:
- `docker run -v HOSTDIR:TARGETDIR IMAGE`
- `docker run -v ~/:/usr/share/nginx/html nginx`

....change the entrypoint:
- `docker run -it --entrypoint EXECUTABLE IMAGE`
- `docker run -it --entrypoint bash nginx`

# Manage Containers------
Show a list of running conatainers:
- `docker ps`

Show a list of all containers:
- `docker ps -a`

Delete a container:
- `docker rm CONTAINER`
- `docker rm web`

Delete a running container:
- `docker rm -f CONTAINER`
- `docker rm -f web`

Delete stopped container:
- `docker container prune`


Copy a file from container to the host:
- `docker cp CONTAINER:SOURCE TARGET`
- `docker cp web:/index.html index.html`

Copy a file from the host to a container:
- `docker cp TARGET CONTAINER:SOURCE`
- `docker cp index.html web:/index.html`

Start a shell inside a running container:
- `docker exec -it CONTAINER EXECUTABLE`
- `docker exec -it web bash`

Rename a container:
- `docker rename OLD_NAME NEW_NAME`
- `docker rename 096 web`

Create an image out of container:
- `docker commit CONTAINER`
- `docker commit web`

# Manage Images------------
Download an image:
- `docker pull IMAGE[:TAG]`
- `docker pull nginx`

Upload an image to a repository:
- `docker push IMAGE`
- `docker push myimage:1.0`

Delete an image:
- `docker rmi IMAGE`

Show a list of all images:
- `docker images`

Delete dangling images:
- `docker image prune`

Delete all unused images:
- `docker image prune -a`

Build an image from a Dockerfile:
- `docker build DIRECTORY`
- `docker build .`

Tag an image:
- `docker tag IMAGE NEWIMAGE`
- `docker tag ubuntu ubuntu:18.04`

Build and tag an image from a Dockerfile:
- `docker build -t IMAGE DIRECTORY`
- `docker build -t myimage`

Save an image to .tar file:
- `docker save IMAGE > FILE`
- `docker save nginx > nginx.tar`

Load an image from a .tar file:
- `docker load -i TARFILE`
- `docker load -i nginx.tar`

# Infor & Stats-------------
Show the logs of  a container:
- `docker logs CONTAINER`
- `docker logs web`

show stats of running containers:
- `docker stats`

Show processes of container:
- `docker top CONTAINER`
- `docker top web`

Show installed docker version:
- `docker version`

Get detailed info about an object
- `docker inspect NAME`
- `docker inspect nginx`

Show all modified files in container:
- `docker diff CONTAINER`
- `docker diff web`

Show mapped ports of a container:
- `docker port CONTAINER`
- `docker port web`


****
See official command from docker: https://dockerlabs.collabnix.com/docker/cheatsheet/
****

** Mostly every command is here. `If i am missed some command here, anyone can add by pull request`