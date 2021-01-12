FROM ubuntu:focal
RUN : \
    && apt-get update \
    && apt install -y software-properties-common \
    && add-apt-repository ppa:deadsnakes/ppa

RUN : \
    && apt-get update \
    && apt-get install -y python3.8 python3-pip python3-venv make build-essential libssl-dev curl vim \
    && apt-get autoremove \
    && apt-get clean

ENV VENV /venv

RUN python3.8 -m venv ${VENV} \
    && ${VENV}/bin/pip install wheel \
    && ${VENV}/bin/pip install Sphinx \
    && ${VENV}/bin/pip install sphinx_rtd_theme

# virtual env entrypoint
COPY entrypoint.sh /opt

# activate it by default
ENTRYPOINT ["/opt/entrypoint.sh"]
