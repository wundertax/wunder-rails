FROM ruby:2.5

RUN mkdir -p /usr/src/rails
WORKDIR /usr/src/rails

COPY Gemfile /usr/src/rails/
COPY Gemfile.lock /usr/src/rails/

RUN bundle config --global frozen 1
RUN bundle install

RUN mkdir -p /usr/src/app

EXPOSE 3000
