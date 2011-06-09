NAME=net-snmp
VERSION=5.4.3

snmpd:
	tar xvzf ${NAME}-$(VERSION).tar.gz

build:
	cd ${NAME}-$(VERSION) && ./configure --prefix=/opt/snmpd --with-defaults --disable-embedded-perl && make && make install
	mkdir -p /opt/snmpd/etc/snmp

package:
	fpm -s dir -t deb -n $(NAME) -v $(VERSION)-heroku-1 -a i386 /opt/snmpd
	
