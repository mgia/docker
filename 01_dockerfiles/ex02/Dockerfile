# Database seeding is the initial seeding of a database with data.

FROM ruby
MAINTAINER mtan
LABEL Description="Containerizes Rails applications"
RUN ["apt-get", "update"]
RUN ["apt-get", "install", "-y", "sqlite3", "nodejs"]
RUN ["gem", "install", "rails"]
COPY ["app","/opt/app"]
WORKDIR /opt/app
ONBUILD RUN ["bundle", "install"]
ONBUILD RUN ["rails", "db:migrate"]
ONBUILD RUN ["rails", "db:seed"]
ONBUILD EXPOSE 3000

# docker build -t ft_rails .
# docker build -f Dockerfile_child -t ex02 .
# docker run -p 3000:3000 ex02
