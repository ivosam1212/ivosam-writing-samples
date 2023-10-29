# tw-mkdocs

## Installation
1. Install docker desktop from https://hub.docker.com/editions/community/docker-ce-desktop-mac
2. Change directory to the tw-mkdocs folder
```bash
cd path/to/project/tw-docops/tw-mkdocs
```
## Build mkdocs image.
Execute the following command in the terminal using the current directory
```bash
docker build -t tw-mkdocs-img .
```

## Serve your local environment.
Execute the following command in the terminal after the docker image creation.
```bash
docker run --name wizeline-mkdocs-template -p 9090:9090 --volume="$PWD:/app" tw-mkdocs-img:latest
```
Note: Use the -d flag in the above command to detach your terminal from the running container.

Start working. Open http://localhost:9090 to see all your changes.
