ARG BUILD_FROM
FROM $BUILD_FROM

# Install requirements for app
RUN \
  apk add --no-cache \
    python3 git

# Python 3 HTTP Server serves the current working dir
# So let's set it to our app persistent data directory.
WORKDIR /data

# Copy data for app
ADD https://github.com/whiteout-project/bot/archive/refs/heads/main.tar.gz /tmp/bot.tar.gz
RUN tar xzf /tmp/bot.tar.gz -C /data && rm /tmp/bot.tar.gz

COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
