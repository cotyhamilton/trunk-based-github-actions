FROM debian:buster-slim

ENV DENO_VERSION=1.6.2

RUN apt-get -qq update \
    && apt-get -qq install -y --no-install-recommends curl ca-certificates unzip \
    && curl -fsSL https://deno.land/x/install/install.sh | sh -s v${DENO_VERSION} \
    && chmod 777 /root/.deno \
    && mv /root/.deno/bin/deno /usr/bin/deno \
    && apt-get -qq remove --purge -y curl ca-certificates unzip \
    && apt-get -qq -y autoremove \
    && apt-get -qq clean 

RUN useradd -ms /bin/bash deno

USER deno

WORKDIR /home/deno

COPY . .

ENTRYPOINT ["deno"]

CMD ["run", "--allow-net", "main.ts"]