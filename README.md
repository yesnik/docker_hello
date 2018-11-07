# Docker Hello

This is a simple example of using docker.

## Requirements

In your system [Docker](https://www.docker.com/) must be installed.

## Installation

### Clone this repo

```
git clone git@github.com:yesnik/docker_hello.git
```

### Bulid an image with the tag 'docker_hello'

```
cd docker_hello
docker build -t docker_hello .
```

### Ensure that the image has been created:

```
docker image ls
```

In the output you must see the repository `docker_hello`.

### Run our custom image

```
docker run --name docker_hello_container -d -p 8080:80 docker_hello
```

*Notes:*
- `--name docker_hello_container` - here we give a name to the container
- `-d` - detaches from the container, running it in the background
- `-p 8080:80` - maps network ports
- `docker_hello` - name of the container we want to run

### Open the page in a browser

On this page you'll see the message from `html/index.html` file: http://127.0.0.1:8080/


### Connect to container

```
docker start docker_hello_container
docker exec -it docker_hello_container sh
```

Executing `run` command with the `-it` flags attaches us to an *interactive tty* in the container.

## Conclusion

In this repo we have created self-contained web server that could easily serve many web documents. We can deploy it on any platform that supports Docker.
