FROM upsilon2gamma/ubuntu-with-build-tools as builder

ENV PG_VER=10.1 PG_DIR=/opt/postgres/${PG_VER}

WORKDIR /tmp
RUN wget https://ftp.postgresql.org/pub/source/v${PG_VER}/postgresql-${PG_VER}.tar.gz
RUN tar xzf postgresql-${PG_VER}.tar.gz
WORKDIR /tmp/postgresql-${PG_VER}
RUN ./configure --prefix=${PG_DIR} && make && make install


FROM ruby:2.5

ENV PG_VER=10.1 PG_DIR=/opt/postgres/${PG_VER}

COPY --from=builder ${PG_DIR} ${PG_DIR}
RUN gem install pg -- --with-pg-dir=${PG_DIR}

VOLUME ["/bundle"]
ENV GEM_HOME=/bundle BUNDLE_PATH=/bundle
WORKDIR "/src"
ENTRYPOINT ["/bin/rails"]
