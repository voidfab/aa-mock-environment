FROM ghcr.io/foundry-rs/foundry:latest

# Copy our source code into the container
WORKDIR /app

# Build and test the source code
COPY . .

EXPOSE 8545

ENV ANVIL_FORK_URL ""
ENV ANVIL_FORK_BLOCK_NUMBER ""

ENTRYPOINT \
  if ! [ -z $ANVIL_FORK_URL ]; then \
    if ! [ -z $ANVIL_FORK_BLOCK_NUMBER ]; then \
      anvil --host 0.0.0.0 --fork-url $ANVIL_FORK_URL --fork-block-number $ANVIL_FORK_BLOCK_NUMBER --no-cors --block-time 1 --silent; \
    else \
      anvil --host 0.0.0.0 --fork-url $ANVIL_FORK_URL --no-cors --block-time 1 --silent; \
    fi; \
  else \
    anvil --host 0.0.0.0 --no-cors --block-time 1 --silent; \
  fi;
