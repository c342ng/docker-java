FROM debian:jessie

ENV LANG C.UTF-8
ENV JAVA_VERSION 8u111
ENV JAVA_HOME /usr/lib/jvm/java-1.8-oracle/jdk
ENV CLASSPATH .:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar 
ENV PATH $PATH:/usr/lib/jvm/java-1.8-oracle/jdk/jre/bin:/usr/lib/jvm/java-1.8-oracle/jdk/bin

ENV CA_CERTIFICATES_JAVA_VERSION 20140324

RUN apt-get update -q && apt-get install -y wget curl ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" vim\
  && apt-get -q clean -y && rm -rf /var/lib/apt/lists/* && rm -f /var/cache/apt/*.bin

RUN mkdir -p "${JAVA_HOME}" \
  && curl -Ls http://download.oracle.com/otn-pub/java/jdk/8u111-b14/jdk-8u111-linux-x64.tar.gz | \
  tar -xz --directory "${JAVA_HOME}" --strip-components=1
