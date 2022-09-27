FROM rust:slim AS builder

ARG PLANTUML_VERSION="1.2022.7"

RUN apt-get update \
    && apt-get dist-upgrade \
    && apt-get install --no-install-recommends -y pkg-config libkrb5-dev libssl-dev curl \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN cargo install mdbook mdbook-mermaid mdbook-plantuml

RUN curl -L https://github.com/plantuml/plantuml/releases/download/v${PLANTUML_VERSION}/plantuml-${PLANTUML_VERSION}.jar -o /usr/local/bin/plantuml.jar \
    && echo '#!/bin/sh' > /usr/local/bin/plantuml \
    && echo '/usr/bin/java -jar /usr/local/bin/plantuml.jar ${@}' >> /usr/local/bin/plantuml \
    && chmod a+rx /usr/local/bin/plantuml

FROM python:3.10-slim

ENV LANG="en_US.UTF-8"

COPY --from=builder /usr/local/cargo/bin/mdbook* /usr/bin/
COPY --from=builder /usr/local/bin/plantuml* /usr/local/bin/

RUN apt-get update \
    && apt-get dist-upgrade -y \
    && apt-get install --no-install-recommends -y npm graphviz openjdk-11-jre \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

LABEL org.opencontainers.image.title "mdbook Builder"
LABEL org.opencontainers.image.description "A minimal image to build mdbook books with mermaid, plantuml, Python 3.10 and javascript dependencies"
LABEL org.opencontainers.image.source "https://github.com/chr1st1ank/arcbook"
LABEL org.opencontainers.image.url "https://github.com/chr1st1ank/arcbook/pkgs/container/arcbook%2Fmdbook-builder"
