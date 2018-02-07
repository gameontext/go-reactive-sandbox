FROM alpine:3.7
ENV RS_ENABLE_CASSANDRA=0
ENV RS_ENABLE_ELASTICSEARCH=0
ADD ./rs-build ./rs-exec /usr/local/bin/
RUN /usr/local/bin/rs-build \
 && echo "/opt/kafka/bin/kafka-topics.sh --list --zookeeper localhost:2181" > /test.sh \
 && chmod +x /test.sh
ADD ./supervisor.d /etc/supervisor.d/
CMD ["/usr/local/bin/rs-exec"]
