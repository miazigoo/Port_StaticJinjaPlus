ARG PYTHON_VERSION="3.12-slim"

FROM python:${PYTHON_VERSION} AS base
FROM base AS build

WORKDIR /opt/app/

RUN --mount=type=bind,source=requirements.txt,target=/opt/app/requirements.txt \
    python -m pip install -r /opt/app/requirements.txt
ADD --checksum=sha256:ea62ec9f5d380c3124af79d95394cdd7c0ebecb4e7756df154ad2b182cebfbb2 https://github.com/MrDave/StaticJinjaPlus/tarball/master /tmp/app.tar.gz

RUN tar -oxzf /tmp/app.tar.gz --strip-components=1 -C /opt/app/ && rm /tmp/app.tar.gz
