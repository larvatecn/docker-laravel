FROM ghcr.io/larvatecn/php:8.1

WORKDIR /app

ENV DEBIAN_FRONTEND noninteractive
ENV TZ=UTC

RUN apt-get update \
    && apt-get install -y supervisor \
    && apt-get -y autoremove && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* \

COPY start-container /usr/local/bin/start-container
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
RUN chmod +x /usr/local/bin/start-container

EXPOSE 8000

ENTRYPOINT ["start-container"]