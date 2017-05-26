# elixir v1.4
#
# docker run --rm pottava/elixir:1.4
# docker run --rm -it pottava/elixir:1.4 iex

FROM pottava/erlang:19

ENV ELIXIR_VERSION=1.4.4

RUN apk --no-cache add --virtual build-dependencies wget ca-certificates \
    && wget --no-check-certificate https://github.com/elixir-lang/elixir/releases/download/v${ELIXIR_VERSION}/Precompiled.zip \
    && mkdir -p /opt/elixir-${ELIXIR_VERSION}/ \
    && unzip Precompiled.zip -d /opt/elixir-${ELIXIR_VERSION}/ \
    && rm Precompiled.zip \
    && apk del --purge -r build-dependencies \
    && rm -rf /etc/ssl

ENV PATH=$PATH:/opt/elixir-${ELIXIR_VERSION}/bin

CMD ["mix", "help"]
