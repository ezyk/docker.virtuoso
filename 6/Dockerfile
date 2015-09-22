FROM debian:7
MAINTAINER Ervis Zyka <ez@eworx.gr>

ENV VIRT_HOME /opt/virtuoso-opensource
ENV VIRT_BUILD_OPTS --with-readline
ENV VIRT_DB /opt/virtuoso-opensource/var/lib/virtuoso/db
ENV PATH $PATH:/opt/virtuoso-opensource/bin

RUN apt-get -y update && \
  apt-get -y install dpkg-dev build-essential openssl autoconf automake libtool flex bison git gperf gawk m4 make libxml2-dev libssl-dev libreadline-dev wget unzip curl vim net-tools && \
  rm -rf /var/lib/apt/lists/* && \
  rm -rf /tmp/*

WORKDIR /opt
RUN git clone git://github.com/openlink/virtuoso-opensource.git virtuoso-opensource.src
WORKDIR /opt/virtuoso-opensource.src
RUN git checkout develop/6
RUN ./autogen.sh && ./configure --prefix=$VIRT_HOME $VIRT_BUILD_OPTS && make && make install

WORKDIR /opt/virtuoso-opensource/share/virtuoso/vad

RUN rm -rf /opt/virtuoso-opensource.src

RUN wget http://opldownload.s3.amazonaws.com/uda/vad-packages/6.1/virtuoso/conductor_dav.vad

VOLUME /opt/virtuoso-opensource/var/lib/virtuoso/db

EXPOSE 1111
EXPOSE 8890

WORKDIR $VIRT_DB
CMD ["virtuoso-t", "-f"]
