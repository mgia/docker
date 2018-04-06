# Run docker build -t ex00 .

FROM alpine
MAINTAINER mtan
LABEL Description="Launches vim from alpine image"
RUN apk update && apk upgrade && apk add vim
ENTRYPOINT vim
