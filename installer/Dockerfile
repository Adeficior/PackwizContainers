FROM eclipse-temurin:25-jre

RUN apt-get update && apt-get install -y curl

ARG MC_HELPER_VERSION=1.61.1
ARG MC_HELPER_REV=1
RUN curl -fsSL https://github.com/itzg/mc-image-helper/releases/download/${MC_HELPER_VERSION}/mc-image-helper-${MC_HELPER_VERSION}.tgz \
  | tar -C /usr/share -zxf - \
  && ln -s /usr/share/mc-image-helper-${MC_HELPER_VERSION}/bin/mc-image-helper /usr/bin

WORKDIR /usr/bin

ENV PATHWIZ_SIDE=both

COPY --chmod=755 setup.sh docker-entrypoint.sh

ENTRYPOINT [ "docker-entrypoint.sh" ]