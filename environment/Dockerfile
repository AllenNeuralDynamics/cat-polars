# hash:sha256:611e22fd9e58e008b75e381c18557fc483354b1aeee4d813648960bf78dda943
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/mambaforge3:23.1.0-4-python3.10.12-ubuntu22.04

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        build-essential=12.9ubuntu3 \
        graphviz=2.42.2-6ubuntu0.1 \
    && rm -rf /var/lib/apt/lists/*

RUN pip3 install -U --no-cache-dir \
    ipykernel==6.29.5 \
    lazynwb==0.2.62 \
    polars[plot,pandas,graph]==1.31.0

COPY postInstall /
RUN /postInstall
