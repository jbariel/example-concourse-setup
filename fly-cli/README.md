# Get fly in a container
Run the concourse docker compose, then download fly, drop it in this folder and run the docker build

## Build
`docker build -t fly:latest .`

## Create a volume
`docker volume create fly-volume`

## Create script
In: `/usr/local/bin`
Named: `fly`
Contents:
```
#!/usr/bin/env bash
FLY_IMG_TAG=latest
# vvv if you're on windows use this vvv
# MOUNT_PATH=$(wslpath -w "$PWD")
# vvv else this vvv
MOUNT_PATH="$PWD"
docker run --network concourse_net --rm -it -v "$MOUNT_PATH":/flydir --mount source=fly-volume,target=/root fly:$FLY_IMG_TAG fly "$@"
```

## Run
`fly --version`
