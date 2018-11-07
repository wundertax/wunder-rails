FROM ruby:2.5

USER root
RUN deps="curl awscli" \
 && apt-get update \
 && apt-get install -y --no-install-recommends $deps \
 && rm -rf /var/lib/apt/lists/*

RUN mkdir -p /usr/src/rails
WORKDIR /usr/src/rails

COPY Gemfile /usr/src/rails/
COPY Gemfile.lock /usr/src/rails/

RUN bundle config --global frozen 1
RUN bundle install

RUN mkdir -p /usr/src/app

EXPOSE 3000
