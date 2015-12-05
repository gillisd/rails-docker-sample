FROM ruby:2.1.5

RUN apt-get update && apt-get install -y build-essential libpq-dev

RUN mkdir /gratr
WORKDIR /gratr

ADD Gemfile /gratr/Gemfile
ADD Gemfile.lock /gratr/Gemfile.lock
RUN bundle install

# Finally, add the rest of our app's code
# (this is done at the end so that changes to our app's code
# don't bust Docker's cache)


ADD . /gratr
EXPOSE 3000

# CMD ["rails", "server", "-b", "0.0.0.0"]
# CMD ["bundle", "exec", "sidekiq", "-q", "data"]
# CMD ["bundle", "exec", "sidekiq", "-q", "ebay"]
# CMD ["bundle", "exec", "sidekiq", "-q", "search", "-e", "production"]
CMD ["fart"]
# CMD ["rake", "resque:work", "QUEUE=jobs"]
# CMD ["whenever", "-w"]