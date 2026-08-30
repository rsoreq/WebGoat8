FROM openjdk:11.0.1-jre-slim-stretch@sha256:965a07951bee0c3b1f8aff4818619ace3e675d91cfb746895e8fb84e3e6b13ca

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