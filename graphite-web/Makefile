NAME=graphite-web
VERSION=0.9.8

graphite-web:
	easy_install --editable --build-directory . "$(NAME)==$(VERSION)"

opt: graphite-web
	cd graphite-web; python setup.py bdist
	cd .. 
	tar xzf graphite-web/dist/graphite-web-$(VERSION).linux-$(shell uname -m).tar.gz

package: opt
	fpm -s dir -t deb -n $(NAME) -v $(VERSION) \
	-p python-$(NAME)-$(VERSION)_all.deb -d "python-django (>> 0), python-cairo (>> 0)" \
	opt	
