FROM mcr.microsoft.com/devcontainers/python:1-3.12-bullseye

RUN apt update && \
    apt install -y \
    build-essential \
    libclang-dev \
    cmake

RUN mkdir -p /opt/hf && chmod 777 /opt/hf && pip install uv

USER vscode

RUN curl https://sh.rustup.rs -sSf | bash -s -- -y
