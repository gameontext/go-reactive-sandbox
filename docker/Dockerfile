FROM alpine:3.7

ADD ./rs-build ./rs-exec /usr/local/bin/
RUN sh -x /usr/local/bin/rs-build \
 && echo "/opt/kafka/bin/kafka-topics.sh --list --zookeeper localhost:2181" > /test.sh \
 && chmod +x /test.sh

RUN mkdir /data && chmod 777 /data
CMD ["/usr/local/bin/rs-exec"]
