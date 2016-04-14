FROM malobato/jdk8:latest

MAINTAINER Miguel Ángel Lobato Álvarez <malobato@coderszone.com>

ENV HOME /home/sts

ADD http://dist.springsource.com/release/STS/3.7.3.RELEASE/dist/e4.5/spring-tool-suite-3.7.3.RELEASE-e4.5.2-linux-gtk-x86_64.tar.gz /tmp/sts.tar.gz

#COPY spring-tool-suite-3.7.3.RELEASE-e4.5.2-linux-gtk-x86_64.tar.gz /tmp/sts.tar.gz

RUN \
	useradd --create-home --home-dir $HOME sts && \
	chown -R sts:sts $HOME

RUN \
	apt-get update && \
	apt-get install -y libswt-gtk-3-jni libswt-gtk-3-java libxslt1-dev libcanberra-gtk3-module packagekit-gtk3-module libwebkitgtk-3.0-0:amd64 git maven && \
	apt-get autoremove && \
	apt-get clean

RUN \
	mkdir /opt/sts && \
	tar xvzf /tmp/sts.tar.gz --directory=/opt/sts && \
	chown -R sts:sts /opt/sts && \
	rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* 

USER sts:sts

WORKDIR $HOME

ENTRYPOINT ["/opt/sts/sts-bundle/sts-3.7.3.RELEASE/STS"]

