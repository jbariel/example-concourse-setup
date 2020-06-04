# Get fly in a container
Run the concourse docker compose, then download fly, drop it in this folder and run the docker build

## Build
`docker build -t fly:latest .`

## Alias
`alias fly='docker run --rm fly:latest fly`

## Run
`fly --version`
