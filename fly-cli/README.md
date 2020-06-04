# Get fly in a container
Run the concourse docker compose, then download fly, drop it in this folder and run the docker build

## Build
`docker build -t fly:latest .`

## Create a volume
`docker volume create fly`

## Alias
`alias fly='docker run --rm --network concourse_net --mount source=fly,target=/root fly:latest fly`

## Run
`fly --version`
