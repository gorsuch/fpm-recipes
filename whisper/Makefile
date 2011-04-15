NAME=whisper
VERSION=0.9.8

whisper:
	easy_install --editable --build-directory . "$(NAME)==$(VERSION)"

usr: whisper
	cd whisper; python setup.py bdist
	cd .. 
	tar xzf whisper/dist/whisper-$(VERSION).linux-$(shell uname -m).tar.gz

package: usr
	fpm -s dir -t deb -n $(NAME) -v $(VERSION) \
	-p python-$(NAME)-$(VERSION)_all.deb -d "python" \
	usr
