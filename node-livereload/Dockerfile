FROM node:alpine

RUN apk add --no-cache \
	build-base \
	ca-certificates \
	git \
	bash

USER node
WORKDIR /opt/app

# stencil port and livereload
EXPOSE 3333 35729