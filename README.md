# README

[![](https://badge.imagelayers.io/softwarecraftsmen/atlassian-jira-servicedesk:latest.svg)](https://imagelayers.io/?images=softwarecraftsmen/atlassian-jira-servicedesk:latest)

## Prepare a docker host

```sh
docker-machine create --driver virtualbox atlassian <1>
docker-machine start atlassian <2>
eval `docker-machine env atlassian` <3>
```

1. Create a docker machine (once only)
2. Start the docker machine
3. Setup the docker client to use the docker-machine

## Run a ServiceDesk instance

```sh
docker pull softwarecraftsmen/atlassian-jira-servicedesk
docker run -d --name servicedesk -p 8080:8080 softwarecraftsmen/atlassian-jira-servicedesk
```

Startup after creating a container takes some time as the installation and configuration process is continuing.
So be patient until the start page for license registration can be opened.

To open the ServiceDesk start page on Mac OSX run from the shell:
```
open http://`docker-machine ip atlassian`:8080
```
