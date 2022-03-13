FROM ubuntu:20.04

RUN apt-get update -y
RUN apt-get install -y python3

EXPOSE 80/udp
EXPOSE 8000/tcp

ENTRYPOINT ["python3", "-m", "http.server"]
