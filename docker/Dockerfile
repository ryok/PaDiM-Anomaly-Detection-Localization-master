FROM nvcr.io/nvidia/pytorch:21.11-py3

ENV DEBIAN_FRONTEND noninteractive
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN apt update

WORKDIR /workspace

COPY pyproject.toml .

RUN apt-get update \
    && apt-get install --no-install-recommends -y curl git build-essential \
    && pip install poetry \ 
    && poetry config virtualenvs.create false \
    && poetry install \
    && rm pyproject.toml
