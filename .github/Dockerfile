FROM rust:slim AS builder

RUN apt-get update \
    && apt-get dist-upgrade \
    && apt-get install -y pkg-config libkrb5-dev libssl-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN cargo install mdbook mdbook-mermaid mdbook-plantuml

FROM debian:stable-slim

RUN apt-get update \
    && apt-get dist-upgrade \
    && apt-get install --no-install-recommends -y npm plantuml graphviz \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

COPY --from=builder /usr/local/cargo/bin/mdbook* /usr/bin/

LABEL org.opencontainers.image.title "mdbook Builder"
LABEL org.opencontainers.image.description "A minimal image to build mdbook books with mermaid, plantuml and javascript dependencies"
LABEL org.opencontainers.image.source "https://github.com/chr1st1ank/arcbook"
LABEL org.opencontainers.image.url "https://github.com/chr1st1ank/arcbook/pkgs/container/arcbook%2Fmdbook-builder"
