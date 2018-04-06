# UDP (User Datagram Protocol) is an alternative communications protocol to Transmission Control Protocol (TCP) used primarily for establishing low-latency and loss tolerating connections between applications on the Internet. Both protocols send short packets of data, called datagrams.
# 9987 (Voice, UDP), 10011 (ServerQuery), 30033 (FileTransfer, TCP), 41144 (DNS)

FROM debian
MAINTAINER mtan
LABEL Description="Launches TeamSpeak server from debian image"
RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y wget bzip2
RUN wget http://dl.4players.de/ts/releases/3.0.13.8/teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2
RUN tar -xjvf teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2
EXPOSE 9987/udp 
EXPOSE 10011
EXPOSE 30033
EXPOSE 41144
WORKDIR /teamspeak3-server_linux_amd64
ENTRYPOINT ./ts3server_minimal_runscript.sh
