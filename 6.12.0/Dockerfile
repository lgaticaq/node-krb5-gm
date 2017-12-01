FROM node:6.12.0-alpine@sha256:3e51d885a8b22aa00dcc68aa53f8080a89d3cac37a74d4b3ca12e69b8c058211

LABEL maintainer "Leonardo Gatica <lgatica@protonmail.com>"

RUN apk add --no-cache --virtual build-dependencies make gcc g++ python && \
  apk add --no-cache krb5-dev imagemagick
RUN apk add --no-cache --repository http://dl-4.alpinelinux.org/alpine/v3.5/community/ graphicsmagick

CMD [ "node" ]
