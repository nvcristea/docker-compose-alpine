FROM nginx:1.11-alpine

MAINTAINER Nicolae V. Cristea <coder@cristea.bid>

# Environments
ENV TIMEZONE        Europe/Bucharest

RUN apk add --update --no-cache \
        tzdata \
        curl \
        git \
        openssh && \
    cp /usr/share/zoneinfo/${TIMEZONE} /etc/localtime && \
    echo "${TIMEZONE}" > /etc/timezone

COPY nginx.vh.default.conf /etc/nginx/conf.d/default.conf
