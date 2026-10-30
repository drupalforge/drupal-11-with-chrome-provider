USER root

RUN apt-get update && \
    apt-get install -y --no-install-recommends jq nano npm && \
    rm -rf /var/lib/apt/lists/*

USER ${USER}
