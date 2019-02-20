# docker-openconnect-chrome
Dockerized openconnect client and chrome web browser.

This [repository](https://github.com/Paldom/docker-openconnect-chrome) contains the Dockerfile of the [dpal/docker-openconnect-chrome](https://hub.docker.com/r/dpal/docker-openconnect-chrome/) image. If you struggle with splint tunneling, with this size-reduced container you can easily connect to a VPN. Preinstalled Chrome browser can be access via VNC.

Forked from: [stephen-fox/chrome-docker](https://github.com/stephen-fox/chrome-docker)

## Usage

### Requirements

Before running a docker image, please ensure:

* IP range of VPN should be different from Docker subnet (Settings > Advanced)
* You've set enough resurces to be available.

### Pull image

#### From Docker Hub

```sh
docker pull dpal/docker-openconnect-chrome:latest
```

#### Or build from GitHub

```sh
docker build -t dpal/docker-openconnect-chrome github.com/paldom/docker-openconnect-chrome
```

### Run docker image

Here's an example how to run this docker container:

```sh
docker run -p 5900:5900 -e VNC_SERVER_PASSWORD=password -e VPN_ARGS="server --user=username" -e BROWSER_ARGS="google.com" --shm-size=2g --privileged --name openconnect dpal/docker-openconnect-chrome
```

### Params

You can use the following environment variables:

* **VNC_SERVER_PASSWORD** - VNC server's password
* **BROWSER_ARGS** - Params passed to Chrome, e.g. `google.com`
* **VPN_ARGS** - `openconnect` arguments, e.g. `server --user=username`

DOck
