# zenn-app/backend/Dockerfile
FROM ruby:2.7

#追加した
RUN gem install rails

ENV LANG C.UTF-8
ENV TZ Asia/Tokyo

RUN mkdir /app
WORKDIR /app

ADD Gemfile /app/Gemfile

# RUN apt-get update -qq && \
#   apt-get install -y build-essential \
#   libpq-dev \
#   sudo \
#   gem install bundler:2.2.20

# RUN bundle install

#以下追加した
# Add a script to be executed every time the container starts.
COPY entrypoint.sh /usr/bin/
RUN chmod +x /usr/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]
EXPOSE 3000

#以下追加した
# Start the main process.
CMD ["rails", "server", "-b", "0.0.0.0"]

ADD . /app