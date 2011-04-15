NAME=carbon
VERSION=0.9.8

carbon:
	easy_install --editable --build-directory . "$(NAME)==$(VERSION)"

opt: carbon
	cd carbon; python setup.py bdist
	cd .. 
	tar xzf carbon/dist/carbon-$(VERSION).linux-$(shell uname -m).tar.gz

package: opt
	fpm -s dir -t deb -n $(NAME) -v $(VERSION) \
	-p python-$(NAME)-$(VERSION)_all.deb -d "python" \
	opt	
