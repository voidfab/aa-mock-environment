# production ready dockerfile that runs pnpm start
FROM node:20-alpine

# set working directory
WORKDIR /app

# install pnpm
RUN npm install -g pnpm

# copy package.json
COPY package.json ./

# copy source code
COPY . .
# COPY ./src ./src
# COPY ./api ./api

# install dependencies
RUN pnpm fetch
RUN pnpm install

EXPOSE 3001

# start app
ENTRYPOINT ["pnpm", "run", "start"]
