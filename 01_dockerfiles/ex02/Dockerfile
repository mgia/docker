# Database seeding is the initial seeding of a database with data.

FROM ruby
MAINTAINER mtan
LABEL Description="Containerizes Rails applications"
RUN ["apt-get", "update"]
RUN ["apt-get", "install", "-y", "sqlite3", "nodejs"]
RUN ["gem", "install", "rails"]
ONBUILD COPY [".","/opt/app"]
ONBUILD WORKDIR /opt/app
ONBUILD RUN ["bundle", "install"]
ONBUILD RUN ["rails", "db:migrate"]
ONBUILD RUN ["rails", "db:seed"]
ONBUILD EXPOSE 3000
