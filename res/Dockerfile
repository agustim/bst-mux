# Based in https://github.com/firecat53/dockerfiles/tree/master/syncthing
FROM ubuntu:trusty

RUN apt-get update && apt-get install -qy ca-certificates
RUN useradd --no-create-home -g users --uid 22000 syncthing
ADD https://github.com/syncthing/syncthing/releases/download/v0.10.27/syncthing-linux-amd64-v0.10.27.tar.gz /syncthing.tar.gz
RUN tar -xzvf syncthing.tar.gz && mv sync*/syncthing /syncthing && rm syncthing.tar.gz
# To use an existing syncthing binary in the root directory, comment out the previous 2 lines and uncomment the next line.
# ADD syncthing /syncthing

USER syncthing

CMD ["/syncthing", "-home=/home/syncthing"]
