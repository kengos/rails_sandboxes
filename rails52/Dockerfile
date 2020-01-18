# syntax = docker/dockerfile:experimental

FROM node:12.14.1-alpine3.11 as nodejs
FROM ruby:2.5.7-alpine3.11 AS build

ENV TZ='Asia/Tokyo' \
    RAILS_ROOT=/opt/rails52

COPY --from=nodejs /usr/local/bin/ /usr/local/bin/
COPY --from=nodejs /usr/local/lib/ /usr/local/lib/
COPY --from=nodejs /opt/ /opt/

RUN : "build tools install" && { \
        apk add --no-cache --virtual=build-dependencies \
            tzdata \
            mysql-dev \
            mysql-client \
            build-base \
            curl \
            curl-dev \
            linux-headers \
            libxml2-dev \
            libxslt-dev \
            yaml-dev \
            zlib-dev \
            gnupg \
            git ; \
    } && \
    : "Set timezone" && {\
      apk --no-cache add tzdata ; \
      cp /usr/share/zoneinfo/${TZ} /etc/localtime ; \
      apk del tzdata ; \
    }

WORKDIR ${RAILS_ROOT}
CMD ["tail", "-f", "/dev/null"]
