NAME=carbon
VERSION=0.9.10

carbon:
	easy_install --editable --build-directory . "$(NAME)==$(VERSION)"

opt: carbon
	cd carbon; python setup.py bdist
	cd .. 
	tar xzf carbon/dist/carbon-$(VERSION).linux-$(shell uname -m).tar.gz

package: opt
	fpm -s dir -t deb -n python-$(NAME) -v $(VERSION)-heroku-1 -a all \
	 -d "python (>> 0)" opt
