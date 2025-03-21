FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive

ARG DEVUSER devuser
ARG DEVUID 1000

RUN apt-get update -y \
 && apt-get install -y gcc g++ git make cmake adduser sudo libfftw3-dev

ENV DEVUSER=${DEVUSER}
RUN adduser --uid ${DEVUID} --disabled-password --gecos "" ${DEVUSER} \
    && echo "${DEVUSER} ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/${DEVUSER}
USER ${DEVUSER} 
