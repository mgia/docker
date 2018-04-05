FROM alpine
MAINTAINER mtan
LABEL Description="Initializes C development environment"
RUN ["apk", "update"]
RUN ["apk", "upgrade"]
RUN ["apk", "add", "man", "man-pages", "mdocml-apropos", "less", "less-doc"]
ENV PAGER less
RUN ["apk", "add", "bc", "vim", "vim-doc", "gcc", "gcc-doc", "make", "make-doc", "git", "git-doc", "valgrind", "valgrind-doc"]
COPY .profile /root
COPY .vimrc /root
WORKDIR /projects
ENTRYPOINT ["/bin/sh"]
