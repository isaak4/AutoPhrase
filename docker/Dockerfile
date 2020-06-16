FROM ubuntu:16.04
ADD https://github.com/shangjingbo1226/AutoPhrase/archive/master.zip /
RUN echo "===> install packages..."  && \
        apt-get update && apt-get install -y --force-yes \
        git \
        make \
        perl \
        g++ \
        openjdk-8-jdk \
        curl \
        vim \
        unzip && \
        unzip master && \
        rm master.zip && \
        mv AutoPhrase-master autophrase && \
        echo "===> compile" && \
        cd /autophrase && bash compile.sh && \
        chmod 755 tools/treetagger/bin/tree-tagger && \

RUN \
    echo "===> clean up..."  && \
    apt-get purge -y --force-yes make && \
    apt-get autoremove -y --purge make && \
    rm -rf /var/cache/oracle-jdk8-installer  && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*


WORKDIR /autophrase
ENV COMPILE 0
