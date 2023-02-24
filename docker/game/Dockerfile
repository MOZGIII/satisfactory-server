ARG FROM

FROM ${FROM}

RUN apt-get update \
  && apt-get install -y \
  ca-certificates \
  gosu

ARG GAME_UID
ARG GAME_GID

RUN groupadd -r \
  -g "${GAME_GID}" \
  game
RUN useradd -mr \
  -s /bin/bash \
  -u "${GAME_UID}" \
  -g "${GAME_GID}" \
  game

COPY ./bin/* /usr/local/bin

ENTRYPOINT ["/usr/local/bin/entrypoint"]
