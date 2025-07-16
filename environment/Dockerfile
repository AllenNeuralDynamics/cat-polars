# hash:sha256:c1eb2302acc560e6624dbda036a2894e4a527cd678cc155d026d1908e3b66fd4
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/mambaforge3:23.1.0-4-python3.10.12-ubuntu22.04

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        build-essential=12.9ubuntu3 \
        graphviz \
    && rm -rf /var/lib/apt/lists/*

RUN pip3 install -U --no-cache-dir \
    ipykernel \
    lazynwb \
    polars[plot,pandas,graph]
