# Docker Hello

This is a simple example of using docker.

## Installation

* Clone this repo

```
git clone git@github.com:yesnik/docker_hello.git
```

* Bulid image with tag 'docker_hello'

```
cd docker_hello
docker build -t docker_hello .
```

* Ensure that image was created:

```
docker image ls
```

In the output you must see repository `docker_hello`.

* Run our custom image

```
docker run --name docker_hello_container -d -p 8080:80 docker_hello
```

*Notes:*

- `--name docker_hello_container` - here we give a name to the container
- `-d` - detaches from the container, running it in the background
- `-p 8080:80` - maps network ports
- `docker_hello` - name of the container we want to run

* Open the page in a browser: http://127.0.0.1:8080/

On this page you'll see message from `html/index.html` file.
