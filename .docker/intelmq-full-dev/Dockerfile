FROM certat/intelmq-full:latest
ENV LANG C.UTF-8

ARG BUILD_DATE
ARG VCS_REF
ARG BUILD_VERSION

LABEL maintainer="IntelMQ Team <intelmq-team@cert.at>" \
      org.opencontainers.image.authors="IntelMQ-Team <intelmq-team@cert.at>" \
      org.opencontainers.image.title="intelmq-full-dev" \
      org.opencontainers.image.description="IntelMQ with core & api" \
      org.opencontainers.image.url="https://intelmq.org/" \
      org.opencontainers.image.source="https://github.com/certtools/intelmq.git" \
      org.opencontainers.image.documentation="https://intelmq.readthedocs.io/en/latest/" \
      org.opencontainers.image.vendor="intelmq-team"


LABEL org.opencontainers.image.created=$BUILD_DATE \
      org.opencontainers.image.revision=$VCS_REF \
      org.opencontainers.image.version=$BUILD_VERSION

WORKDIR /opt
ADD entrypoint-dev.sh /opt/entrypoint-dev.sh
ADD install_reqs_and_deploy_bots /opt/install_reqs_and_deploy_bots.sh
RUN sudo chmod +x /opt/entrypoint-dev.sh \
    && sudo chown intelmq:intelmq /opt/entrypoint-dev.sh
RUN sudo chmod +x /opt/install_reqs_and_deploy_bots.sh \
    && sudo chown intelmq:intelmq /opt/install_reqs_and_deploy_bots.sh

USER intelmq:intelmq

ENTRYPOINT [ "/opt/entrypoint-dev.sh" ]
