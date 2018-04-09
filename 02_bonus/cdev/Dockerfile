FROM alpine
MAINTAINER mtan
LABEL Description="Initializes C development environment"
RUN ["apk", "update"]
RUN ["apk", "upgrade"]
RUN ["apk", "add", "man", "man-pages", "mdocml-apropos", "less", "less-doc"]
ENV PAGER less
RUN ["apk", "add", "bc", "vim", "vim-doc", "gcc", "gcc-doc", "make", "make-doc", "git", "git-doc"]
ONBUILD COPY ~/.vimrc /root
ONBUILD COPY ~/.bash_profile /root
WORKDIR /projects
ENTRYPOINT ["/bin/sh"]
