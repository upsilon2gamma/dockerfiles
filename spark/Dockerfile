from openjdk:8

COPY ./sources.list /etc/apt/sources.list

ENV UPDATED_AT=1505531520

RUN apt-get update && apt-get install build-essential zlib1g-dev -y
ADD ./spark-2.2.0-bin-hadoop2.7.tgz /opt
ENV SPARK_HOME="/opt/spark-2.2.0-bin-hadoop2.7"
ADD ./Python-3.6.3.tgz /root
WORKDIR /root/Python-3.6.3
RUN ./configure --prefix=/opt/Python-3.6.3 --enable-optimizations && make && make install && make clean

WORKDIR /opt/Python-3.6.3/bin
RUN ln -s pip3 pip && ln -s pydoc3 pydoc && ln -s python3 python && ln -s python3-config python-config
ENV PATH="$SPARK_HOME/bin:/opt/Python-3.6.3/bin:${PATH}"

WORKDIR /root
