# NodeJS + Livereload Image

Standard node image that exposes port 3333 and 35729. 
Built for StencilJS development.

## Build

```
docker build -t node-livereload .
```

## Run

```
docker run -it \
    --name  my-stencil-project \ 
    -p 3333:3333 \
    -p 35729:35729 \
    -v "${PWD}:/home/user/app" \
    --entrypoint bash \
    node-livereload
```