# production ready dockerfile that runs pnpm start
FROM node:20-alpine

# set working directory
WORKDIR /app

# Install additional dependencies
RUN apk add --no-cache git

# install pnpm
RUN npm install -g pnpm@^8.15

# copy source code
COPY . .

# install dependencies
RUN pnpm fetch
RUN pnpm install

# EXPOSE 4000
EXPOSE 4337

# start app
ENTRYPOINT ["pnpm", "run", "start"]
