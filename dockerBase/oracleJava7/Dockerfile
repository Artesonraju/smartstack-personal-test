FROM debian:8.0

MAINTAINER  Etienne Molto "molto.etienne@gmail.com"

# preselect license acceptation, add ppa and install oracle java 7
RUN \
    echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections && \
    echo "deb http://ppa.launchpad.net/webupd8team/java/ubuntu precise main" | tee /etc/apt/sources.list.d/webupd8team-java.list && \
    echo "deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu precise main" | tee -a /etc/apt/sources.list.d/webupd8team-java.list && \
    apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys EEA14886 && \
    apt-get update && \
    apt-get install -y oracle-java7-installer && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf /var/cache/oracle-jdk7-installer

# commonly used JAVA_HOME variable
ENV JAVA_HOME /usr/lib/jvm/java-7-oracle
