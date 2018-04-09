# docker run -it -v /projects:/projects {image_name}

FROM debian
MAINTAINER mtan
LABEL Description="Preparing Valgrind Environment"
RUN apt-get -y update
RUN apt-get -y upgrade
RUN apt-get install -y gcc make valgrind vim

ONBUILD COPY ~/.zshrc /root
ONBUILD COPY ~/.bash_profile /root

USER root

WORKDIR projects
