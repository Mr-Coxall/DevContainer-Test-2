FROM linuxcontainers/debian-slim:latest

RUN apt-get update \
	&& apt-get install -y \
	curl \
	sudo \
	git \
	gh \
	default-jdk \
	python3 \
	python-is-python3 \
	python3-pip \
	vim \
	wget \
	&& rm -rf /var/lib/apt/lists/*

ARG USER=coder
RUN useradd --groups sudo --no-create-home --shell /bin/bash ${USER} \
	&& echo "${USER} ALL=(ALL) NOPASSWD:ALL" >/etc/sudoers.d/${USER} \
	&& chmod 0440 /etc/sudoers.d/${USER}
USER ${USER}
WORKDIR /home/${USER}