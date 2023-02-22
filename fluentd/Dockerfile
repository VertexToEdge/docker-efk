
FROM fluent/fluentd:v1.15.3-debian-1.2

USER root

RUN buildDeps="sudo make gcc g++ libc-dev" \
 && apt-get update \
 && apt-get install -y --no-install-recommends $buildDeps \
 && sudo gem install elasticsearch -v 7.8 \
 && sudo gem install fluent-plugin-elasticsearch -v 4.0.1 \
 && sudo gem sources --clear-all \
 && SUDO_FORCE_REMOVE=yes \
 apt-get purge -y --auto-remove \
    -o APT::AutoRemove::RecommendsImportant=false \
    $buildDeps \
 && rm -rf /var/lib/apt/lists/* \
 && rm -rf /tmp/* /var/tmp/* /usr/lib/ruby/gems/*/cache/*.gem

USER fluent