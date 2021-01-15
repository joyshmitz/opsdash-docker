# OpsDash Dockerfile

This is a Dockefile to easily setup the [OpsDash](https://www.opsdash.com)-Server with docker.

## Install & Setup

- Create an account on [OpsDash](https://www.opsdash.com).
- Server into the `dep`-directory `dep/opsdash-server_1.12.2_amd64.deb`.
- Before starting the OpsDash server, you should edit the configuration file at /etc/opsdash/server.cfg, at least to review that the default settings are acceptable.
- Agent downloah here https://packages.rapidloop.com/downloads/opsdash-agent_1.12.2_amd64.deb
- Before the agent can be started, the agent configuration file at /etc/opsdash/agent.cfg, needs to be edited.

### Build with docker

Build the docker image:

```bash
docker build -t opsdash-server .
```

### Pull and Run the container from (https://hub.docker.com):

```bash
docker run -d -p 8086:8086 -p 6273:6273 -p 6273:6273/udp joyshmitz/opsdash-server:latest
```

### Build & Run with docker-compose

```bash
docker-compose -p opsdash-server build
docker-compose -p opsdash-server up
```
This is an unofficial image.
