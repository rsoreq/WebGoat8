FROM openjdk:11.0.3-jre-slim-stretch@sha256:49b7efb61374586c9c007adc306dcaf248ba4250286a9a40d7f0b9a546f0bb25

ARG webwolf_version=v8.0.0-SNAPSHOT

RUN \
  apt-get update && apt-get install && \
  useradd --home-dir /home/webwolf --create-home -U webwolf

USER webwolf
COPY target/webwolf-${webwolf_version}.jar /home/webwolf/webwolf.jar
COPY start-webwolf.sh /home/webwolf

EXPOSE 9090

ENTRYPOINT ["/home/webwolf/start-webwolf.sh"]
CMD ["--server.port=9090", "--server.address=0.0.0.0"]