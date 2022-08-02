ARG ELK_VERSION

# https://www.docker.elastic.co/
USER root
FROM docker.elastic.co/elasticsearch/elasticsearch:${ELK_VERSION}
RUN chown -R root /usr/share/filebeat/
RUN chmod -R go-w /usr/share/filebeat/
RUN filebeat -e  -strict.perms=false \
  -E output.elasticsearch.hosts=["0.0.0.0::9200"]
