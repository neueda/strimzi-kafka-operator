FROM strimzi/base:latest

LABEL org.opencontainers.image.source='https://github.com/strimzi/strimzi-kafka-operator'

ARG KAFKA_DIST_DIR
ARG KAFKA_VERSION
ARG THIRD_PARTY_LIBS
ARG strimzi_version
ARG TARGETPLATFORM

RUN zypper --non-interactive install gettext-tools nmap netcat-openbsd stunnel net-tools unzip hostname findutils tar \
    && zypper cc -a

RUN useradd -r -m -u 1001 -g 0 kafka

ENV KAFKA_HOME=/opt/kafka
ENV KAFKA_VERSION=${KAFKA_VERSION}
ENV STRIMZI_VERSION=${strimzi_version}