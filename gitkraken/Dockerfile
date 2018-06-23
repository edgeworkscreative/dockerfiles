FROM debian:buster

# Tell debconf to run in non-interactive mode
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -y \
	apt-transport-https \
	ca-certificates \
	curl \
	wget \
	gnupg \
	gconf2 \
	gconf-service \
	python \
	gvfs-bin \
	xdg-utils \
	--no-install-recommends

# Needed to install libgnome-keyring0
RUN echo "deb [arch=amd64] http://httpredir.debian.org/debian jessie main contrib non-free" > /etc/apt/sources.list.d/jessie.list

RUN apt-get update && apt-get -y install \
	git \
	libasound2 \
	libatk1.0-0 \
	libcairo2 \
	libcups2 \
	libexpat1 \
	libfontconfig1 \
	libfreetype6 \
	libgtk2.0-0 \
	libpango-1.0-0 \
	libx11-xcb1 \
	libxcomposite1 \
	libxcursor1 \
	libxdamage1 \
	libxext6 \
	libxfixes3 \
	libxi6 \
	libxrandr2 \
	libxrender1 \
	libxss1 \
	libxtst6 \
	openssh-client \
	libgnome-keyring0 \
	libnotify4 \
	libnss3 \
	libxkbfile1 \
	--no-install-recommends \
	&& rm -rf /var/lib/apt/lists/*

# Install GitKraken
RUN  wget --quiet "https://release.gitkraken.com/linux/gitkraken-amd64.deb" -O /gitkraken-amd64.deb && dpkg -i /gitkraken-amd64.deb && rm /gitkraken-amd64.deb

ENV HOME /home/user
RUN useradd --create-home --home-dir $HOME user && chown -R user:user $HOME

COPY start.sh /usr/local/bin/start.sh

WORKDIR $HOME

CMD [ "start.sh" ]