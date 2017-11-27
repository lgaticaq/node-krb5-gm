FROM lgatica/node-krb5-gm:9.2.0@sha256:a333957c9c5ecdb28f474ac6c58f4acf460d34cb8bf153a41bafff54f43ffa8a

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

ONBUILD ARG NODE_ENV
ONBUILD ENV NODE_ENV $NODE_ENV
ONBUILD COPY package.json package-lock.* yarn.* /usr/src/app/
ONBUILD RUN if [ -e yarn.lock ]; \
  then yarn && yarn cache clean; \
  else npm i && npm cache clean --force; fi && \
  apk del build-dependencies && \
  rm -rf ~/.node-gyp /tmp/*
ONBUILD COPY . /usr/src/app

CMD [ "npm", "start" ]
