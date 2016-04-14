FROM ubuntu:trusty

MAINTAINER Miguel Ángel Lobato Álvarez <malobato@coderszone.com>

RUN \
	apt-get update && \
	
	# JDK 8 Repositories
	echo "deb http://ppa.launchpad.net/webupd8team/java/ubuntu trusty main" | tee /etc/apt/sources.list.d/webupd8team-java.list && \
	
	echo "deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu trusty main" | tee -a /etc/apt/sources.list.d/webupd8team-java.list && \
	
	apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys EEA14886 && \
	
	apt-get update && \

	# Accept Oracle JDK 8 license automatically
	echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | sudo /usr/bin/debconf-set-selections && \

	apt-get install -y oracle-java8-installer && \

	apt-get install -y oracle-java8-set-default && \

	apt-get install -y maven && \

	apt-get autoremove && \

	apt-get clean && \

	rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /var/cache/oracle-jdk8-installer

ENV JAVA_HOME /usr/lib/jvm/java-8-oracle
