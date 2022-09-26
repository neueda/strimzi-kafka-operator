FROM opensuse/leap:15.3

LABEL org.opencontainers.image.source='https://github.com/strimzi/strimzi-kafka-operator'

ARG JAVA_VERSION=11
ARG TARGETPLATFORM

USER root

RUN zypper refresh \
    && zypper --non-interactive install java-${JAVA_VERSION}-openjdk openssl shadow curl \
    && zypper cc -a

ENV JAVA_HOME /usr/lib/jvm/jre-11

ENV TINI_VERSION v0.19.0
ENV TINI_SHA256_AMD64=93dcc18adc78c65a028a84799ecf8ad40c936fdfc5f2a57b1acda5a8117fa82c

RUN curl -s -L https://github.com/krallin/tini/releases/download/${TINI_VERSION}/tini -o /usr/bin/tini; \
    echo "${TINI_SHA256_AMD64} */usr/bin/tini" | sha256sum -c; \
    chmod +x /usr/bin/tini;