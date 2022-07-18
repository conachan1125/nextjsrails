FROM ruby:3.1.2

ENV BUNDLE_VERSION 2.3.7
ENV APP /usr/src/app

# netcat is for nc command
RUN apt-get update && apt-get install netcat && apt-get install vim
RUN gem install bundler --version "$BUNDLE_VERSION" 

RUN mkdir $APP
WORKDIR $APP

COPY Gemfile* $APP/
RUN bundle install

COPY . $APP/

CMD ["./bin/server-dev"]