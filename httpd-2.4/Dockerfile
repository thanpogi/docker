FROM thanpogi/oraclelinux-6.6
MAINTAINER Jonathan Lonceras <jonathan.lonceras@fujixerox.com>

## Installing httpd2.4
RUN \
	yum -y install apr-devel && \
	yum -y install apr-util-devel && \
	yum -y install pcre-devel && \
	mkdir tmp && \
	cd tmp && \
	wget http://archive.apache.org/dist/httpd/httpd-2.4.20.tar.gz && \
	gzip -d httpd-2.4.20.tar.gz && \
	tar xvf httpd-2.4.20.tar && \
	wget http://archive.apache.org/dist/apr/apr-1.5.1.tar.gz && \
	gzip -d apr-1.5.1.tar.gz && \
	tar xvf apr-1.5.1.tar && \
	wget http://archive.apache.org/dist/apr/apr-util-1.5.1.tar.gz && \	
	gzip -d apr-util-1.5.1.tar.gz && \
	tar xvf apr-util-1.5.1.tar && \	
	mv apr-1.5.1 httpd-2.4.20/srclib/apr && \
	mv apr-util-1.5.1 httpd-2.4.20/srclib/apr-util && \
	mv httpd-2.4.20 /usr/src/ && \
	cd /usr/src/httpd-2.4.20 && \
	./configure --enable-ssl --enable-so --with-included-apr && \
	make && \
	make install && \
	rm -f /usr/local/apache2/logs/httpd.pid

## Clean the package caches	
RUN yum -y clean all

CMD /usr/local/apache2/bin/httpd -DFOREGROUND