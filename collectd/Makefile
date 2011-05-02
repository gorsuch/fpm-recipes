NAME=collectd
VERSION=4.9.4

collectd:
	wget http://collectd.org/files/collectd-$(VERSION).tar.gz
	tar xvzf collectd-$(VERSION).tar.gz

build: collectd
	cd collectd-$(VERSION) && ./configure && make install

package: build
	fpm -s dir -t deb -n $(NAME) -v $(VERSION)-custom-1 -a i386 /opt/collectd
	
