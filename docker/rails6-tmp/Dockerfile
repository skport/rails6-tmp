FROM ruby:2.6

# throw errors if Gemfile has been modified since Gemfile.lock
RUN bundle config --global frozen 1

# Move working directory for docker
WORKDIR /tmp

# Install Node.js
RUN apt update -y \
    ; \
    apt install nodejs -y \
    ; \
    apt install npm -y

# Install yarn
RUN npm install -g yarn -y

# Install Rails
ADD Gemfile /tmp/
ADD Gemfile.lock /tmp/
RUN gem install rails -v 6.0.3 \
    ; \
    rails webpacker:install \
    ; \
    bundle install

# Move to current directory
WORKDIR /rails

# Start the Rails server
CMD ["rails", "s", "-p", "3000", "-b", "0.0.0.0"]