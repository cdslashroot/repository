FROM ubuntu:18.04

ENV LANG C.UTF-8

# Copy data for add-on
COPY run.sh /
RUN chmod a+x /run.sh

RUN dpkg --add-architecture armhf

RUN apt-get update && apt-get install -y wget libc6:armhf libstdc++6:armhf

RUN wget https://bin.equinox.io/c/VdrWdbjqyF/cloudflared-stable-linux-arm.deb

RUN dpkg -i ./cloudflared-stable-linux-arm.deb

EXPOSE 5053

CMD [ "/run.sh" ]
