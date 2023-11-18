ARG IMAGE=ubuntu:latest
ARG USER=coder

FROM ${IMAGE}

# install usage develop utilities
RUN apt-get update \
	&& apt-get install -y \
	curl \
	git \
	golang \
	sudo \
	vim \
	wget \
	&& rm -rf /var/lib/apt/lists/*

# install docker
RUN curl -fsSL https://get.docker.com | sh

# add user
RUN useradd --groups sudo --no-create-home --shell /bin/bash ${USER} \
	&& echo "${USER} ALL=(ALL) NOPASSWD:ALL" >/etc/sudoers.d/${USER} \
	&& chmod 0440 /etc/sudoers.d/${USER}
USER ${USER}
WORKDIR /home/${USER}
