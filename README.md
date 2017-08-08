# NodeJS in Docker

## Overview

This is a simple example to understand the basics of **Docker** with the help of a simple NodeJS web app.

## Dependencies

### Runtime dependencies

The following libraries are used in the application.

*[Express](https://expressjs.com/)*: Fast, unopinionated, minimalist web framework for Node.js

*[Docker](https://www.docker.com/)*: Docker is a software container platform.

### Dev dependencies

The following libraries are used for the development of this project.

*[npm](https://www.npmjs.com/)*: Package manager.

## How to...

### Build and run

To build the Docker image go into the root folder of this project where the `Dockerfile` is located and run:

```
sudo docker build -t <your username>/<name of web app> .
```

With the `-t` flag you can set a tag to easily identify the image later.

The image will now be listed by Docker.

```
sudo docker images
```

Running the image with `-d` runs the container in detached mode, leaving the container running in the background. The `-p` flag redirects a public port to a private port inside the container.

```
sudo docker run -p 12345:8080 -d <your username>/<name of web app>
```

To see that the app is working you can execute the following command.

```
curl -i localhost:12345
```

Which sould give back a similar response.

```
HTTP/1.1 200 OK
X-Powered-By: Express
Content-Type: text/html; charset=utf-8
Content-Length: 12
Connection: keep-alive

Hello world
```
