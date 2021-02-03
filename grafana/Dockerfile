FROM grafana/grafana:5.4.3

USER root
RUN apt-get update && apt-get install -y curl gettext-base && rm -rf /var/lib/apt/lists/*

USER grafana
WORKDIR /etc/grafana
COPY datasources ./datasources

WORKDIR /app
COPY entrypoint.sh ./

USER root
RUN chmod u+x entrypoint.sh

ENTRYPOINT ["/app/entrypoint.sh"]
