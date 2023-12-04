# Use a smaller base image
FROM ubuntu:22.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y --no-install-recommends \
    curl \
    python3 \
    python3-pip \
    python3-venv \
    xz-utils \
    nodejs \
    npm \
    openjdk-17-jdk \
    && curl -L "https://github.com/koalaman/shellcheck/releases/download/v0.9.0/shellcheck-v0.9.0.linux.x86_64.tar.xz" | tar -xJ \
    && mv "shellcheck-v0.9.0/shellcheck" /usr/bin/ \
    && chmod +x /usr/bin/shellcheck \
    && pip3 install --upgrade pip \
    && pip3 install pylint==3.0.2 \
    && npm install -g npm-groovy-lint@13.0.0 \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /shellcheck-v0.9.0

ENV PATH /usr/local/bin:$PATH

WORKDIR /workspace

CMD ["bash"]
