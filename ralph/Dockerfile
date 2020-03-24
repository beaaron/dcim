FROM	node:latest

LABEL	maintainer="beaaron" \
	email="aaronditzler@gmail.com" \
	version="1.0.0"

ENV	WEBSERVER_MOUNT="/var/www" \
	WEBSERVER_CONTENT="/var/www/public" \
	GIT_CLONE_TEMP="/tmp/ralph"

RUN	set -eux; \
	mkdir -p "$WEBSERVER_CONTENT"; \
	mkdir -p "$GIT_CLONE_TEMP"; \
	git clone https://github.com/beaaron/dcim.git $GIT_CLONE_TEMP; \
	mv $GIT_CLONE_TEMP/webserver/public/*.html $WEBSERVER_CONTENT

WORKDIR	$WEBSERVER_MOUNT

EXPOSE	80/tcp

CMD	npx http server --port 80


