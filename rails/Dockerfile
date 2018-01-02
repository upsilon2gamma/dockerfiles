FROM ruby

RUN apt-get update && apt-get install node -y && apt-get clean
RUN gem install rails

WORKDIR "/src"
ENTRYPOINT ["rails"]
