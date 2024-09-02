ARG NODE_VERSION=22
FROM node:${NODE_VERSION}

LABEL maintainer=chuk

WORKDIR /app

COPY package*.json .
COPY main.js .
COPY public public
COPY views views

RUN npm ci

ENV PORT=3000 INSTANCE_NAME=dov-bear INSTANCE_HASH=abcd1234

HEALTHCHECK --interval=30s --timeout=5s --start-period=5s --retries=3 \
   CMD curl -s localhost:${PORT}/healthz || exit 1

EXPOSE ${PORT}

ENTRYPOINT node main
