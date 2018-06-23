## Build

```
docker docker build -t gitkraken .
```

## Run

```
docker run -d \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    -v $HOME:/home/user \
    -e DISPLAY=unix$DISPLAY \
    --device /dev/dri \
    --name gitkraken \
    gitkraken
```

or

```
docker run -d \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    -v $HOME:/home/user \
    -v "/var/www:/var/www" \
    -e DISPLAY=unix$DISPLAY \
    --device /dev/dri \
    --name gitkraken \
    gitkraken
```