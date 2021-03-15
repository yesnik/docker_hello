# Docker Hello

This is an example of using Docker. Look inside `Dockerfile`, it's based on the official [nginx](https://hub.docker.com/_/nginx) image.

Ensure that your PC have [Docker](https://www.docker.com/) installed.


## Installation

1. Clone this repo
```bash
git clone git@github.com:yesnik/docker_hello.git
```

2. Bulid an image with the repo name `docker_hello` and tag `1.0`
```bash
cd docker_hello
docker build -t docker_hello:1.0 .
```

3. Ensure that the image has been created
```bash
docker images
```

4. Create container based on our image
```bash
docker run --name docker_hello_container -d -p 8080:80 docker_hello:1.0
```

*Params:*
- `--name docker_hello_container` - name of the created container
- `-d` - detaches from the container, running it in the background
- `-p 8080:80` - maps network ports. Your host's port 8080 will be mapped to container's 80 port
- `docker_hello:1.0` - image's name

5. Visit page: http://127.0.0.1:8080/. You'll see the message from `index.html` file.

### Play with the container

1. Look at the running containers
```bash
docker ps
```

2. Connect to the container and use bash
```bash
docker exec -it docker_hello_container bash
```

Flag `-it` attaches us to an *interactive tty* in the container.

3. To exit container press `Ctrl + D`

4. Stop the container
```bash
docker stop docker_hello_container
```

5. Remove the container
```bash
docker rm docker_hello_container
```

6. Ensure that the container has been deleted
```bash
docker ps -a
```
You won't see `docker_hello_container` in the list.

## Conclusion

In this repo we have created self-contained web server that could easily serve many web documents.
We can deploy it on any server with Docker.
