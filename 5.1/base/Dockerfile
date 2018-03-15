FROM ruby:2.5

LABEL name="wunder-rails" \
    description="wundertax ruby base image" \
    maintainer="tech-services@wundertax.de"

RUN deps="curl awscli" \
 && apt-get update \
 && apt-get install -y --no-install-recommends $deps \
 && rm -rf /var/lib/apt/lists/* \
 && mkdir -p /usr/src/rails

WORKDIR /usr/src/rails

COPY Gemfile /usr/src/rails/
COPY Gemfile.lock /usr/src/rails/

RUN bundle config --global frozen 1 \
 && bundle install \
 && mkdir -p /usr/src/app

EXPOSE 3000
