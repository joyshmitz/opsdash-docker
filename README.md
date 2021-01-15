# OpsDash Dockerfile

This is a Dockefile to easily setup the [OpsDash](https://www.opsdash.com)-Server with docker.

## Install & Setup

- Create an account on [OpsDash](https://www.opsdash.com).
- Server into the `dep`-directory `dep/opsdash-server_1.12.2_amd64.deb`.
- Change the config in `server.cfg` to your needs.

### Build with docker

Build the docker image:

```bash
docker build -t opsdash-server .
```

### Pull and Run the container from hub.docker.com:

```bash
docker run -d -p 8086:8086 -p 6273:6273 -p 6273:6273/udp joyshmitz/opsdash-server:latest
```

### Run with docker-compose

```
docker-compose -p opsdash-server build
docker-compose -p opsdash-server up
```
