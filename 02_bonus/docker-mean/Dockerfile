# Run Mongo in separate container
# docker pull mongo
# docker run -p 27017:27017 -d --name db mongo

FROM ubuntu:14.04
MAINTAINER mtan
LABEL Description="Creating envirnment for MEAN stack"

# Exposing ports for Node.js (3000), MongoDB (27017) and LiveReload (35729)
EXPOSE 3000 27017 35729

RUN apt-get update && apt-get install -y -qq \
  git \
  curl \
  ssh \
  gcc \
  make \
  build-essential \
  sudo \
  apt-utils \
  && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Install Node.js
RUN curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash - \
  && apt-get install -y -q nodejs \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Install bower and gulp globally
RUN npm install --quiet -g bower gulp \
  && npm cache clean

# Create workdir
RUN mkdir -p /usr/src/app
WORKDIR /user/src/app

# Clone Mean.io repository
RUN git clone https://github.com/linnovate/mean.git /user/src/app

# Install server dependencies using npm
RUN npm install --quiet && npm cache clean

# Install client dependencies using bower
RUN bower install --config.interactive=false --quiet --allow-root

# Start server
CMD ["gulp"]

