FROM azul/zulu-openjdk-alpine:16-latest

LABEL author="eugeniodevv"

LABEL org.opencontainers.image.source="https://github.com/eugeniodevv/azul-zulu-pterodactyl"
LABEL org.opencontainers.image.licenses=WTFPL

RUN apt update -y \
	&& apt install -y \
		curl lsof ca-certificates openssl git tar sqlite3 fontconfig tzdata iproute2 libfreetype6 libstdc++6 libargon2-dev

ENV LC_ALL=C.UTF-8
ENV LANG=C.UTF-8
ENV LANGUAGE=C.UTF-8

RUN useradd -d /home/container -m container

USER container
ENV USER=container HOME=/home/container
WORKDIR /home/container

COPY ./../entrypoint.sh /entrypoint.sh
CMD [ "/bin/bash", "/entrypoint.sh" ]