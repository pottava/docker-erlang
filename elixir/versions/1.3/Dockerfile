# elixir v1.3
#
# docker run --rm pottava/elixir:1.3 mix help
# docker run --rm -it pottava/elixir:1.3 iex

FROM pottava/erlang:18

ENV ELIXIR_VERSION=1.3.2

RUN apk --no-cache add --virtual build-dependencies wget ca-certificates \
    && wget --no-check-certificate https://github.com/elixir-lang/elixir/releases/download/v${ELIXIR_VERSION}/Precompiled.zip \
    && mkdir -p /opt/elixir-${ELIXIR_VERSION}/ \
    && unzip Precompiled.zip -d /opt/elixir-${ELIXIR_VERSION}/ \
    && rm Precompiled.zip \
    && apk del build-dependencies \
    && rm -rf /etc/ssl

ENV PATH=$PATH:/opt/elixir-${ELIXIR_VERSION}/bin

CMD ["mix"]
