FROM debian:11-slim

RUN set -eux && \
	apt update -y && \
	apt install -y wget bash && \
	apt clean -y && \
	rm -rf /var/lib/apt/lists/* && \
	wget --no-check-certificate -qO- 'https://github.com/DDS-Derek/nas-tools-Docker/raw/master/debian.base/py_3.10.11.sh' | bash