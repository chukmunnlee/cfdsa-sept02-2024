ARG NODE_VERSION=22

FROM library/node

LABEL maintainer=chuk
LABEL build_on="Sept 2 2024"

## How to build

# create a directory /app and cd /app
WORKDIR /app

# Inside /app
# Copy my src

# copy from local container
COPY main.js .
COPY package*.json .
COPY public public
COPY views views

# install node modules
RUN npm ci

## How to run
ENV APP_PORT=5000 

# What are the exposed port
EXPOSE ${APP_PORT}

# Run the application
ENTRYPOINT node main