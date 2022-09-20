FROM rust:slim AS builder

RUN apt-get update \
 && apt-get install -y gcc libkrb5-dev libssl-dev pkg-config

COPY cargo-config.toml $HOME/.cargo/config.toml
RUN cargo install mdbook mdbook-mermaid mdbook-plantuml

FROM debian:stable-slim

RUN apt-get update \
 && apt-get dist-upgrade \
 && apt-get install -y npm plantuml \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

COPY --from=builder /usr/local/cargo/bin/mdbook* /usr/bin/

COPY cargo-config.toml $HOME/.cargo/config.toml
RUN cargo install mdbook-mermaid mdbook-plantuml
RUN cargo install mdbook
