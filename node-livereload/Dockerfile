FROM alpine:latest

RUN apk add --no-cache \
    git \
    bash \
	nodejs \
	python

ENV USER user
ENV HOME /home/$USER

RUN addgroup -g 1000 -S $USER && adduser -u 1000 -S $USER -G $USER

USER $USER

RUN mkdir $HOME/app
RUN mkdir $HOME/.npm-global && npm config set prefix $HOME/.npm-global && NPM_CONFIG_PREFIX=$HOME/.npm-global
RUN npm install npm@latest -g

WORKDIR $HOME/app

# stencil port and livereload
EXPOSE 3333 35729