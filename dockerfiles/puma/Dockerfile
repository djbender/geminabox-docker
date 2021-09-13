FROM ruby

RUN gem install --no-document geminabox:1.2 puma
RUN mkdir -p /webapps/geminabox/config && \
	mkdir -p /webapps/geminabox/data

RUN mkdir -p /tmp
RUN chmod o+t /tmp

WORKDIR /webapps/geminabox/config
COPY assets/conf/config.ru /webapps/geminabox/config/config.ru

# default server config
COPY assets/server_config/config.ru /webapps/server/config/config.ru

COPY assets/entrypoint.sh /webapps/server

ENTRYPOINT ["/webapps/server/entrypoint.sh"]
