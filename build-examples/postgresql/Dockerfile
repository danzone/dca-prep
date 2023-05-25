ARG VERSION=20.04

FROM ubuntu:${VERSION}

LABEL creator="Daniele Gagliardi"

ENV TZ=Europe/Rome
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get update && apt-get install -y postgresql postgresql-contrib \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

EXPOSE 5432

ENTRYPOINT service postgresql start && tail -f /var/log/postgresql/postgresql-12-main.log
