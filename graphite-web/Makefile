NAME=graphite-web
VERSION=0.9.10

graphite-web:
	easy_install --editable --build-directory . "$(NAME)==$(VERSION)"

opt: graphite-web
	cd graphite-web; python setup.py bdist
	cd .. 
	tar xzf graphite-web/dist/graphite-web-$(VERSION).linux-$(shell uname -m).tar.gz

package: opt
	fpm -s dir -t deb -n python-$(NAME) -v $(VERSION)-heroku-1 -a all \
	-d "python-django (>> 0), python-cairo (>> 0), python-carbon (>> 0), python-whisper (>> 0), python-django-tagging (>> 0)" opt
