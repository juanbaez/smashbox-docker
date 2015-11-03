# Smashbox test environment

https://hub.docker.com/r/juanbaez/smashbox-docker/

To run a test just run the following:

	docker run -e OC_ACCOUNT_PASSWORD=superSecret123 \
		-e OC_SERVER=123.45.67.89 \
		-e OC_ROOT=owncloud \
		-e OC_ADMIN_USER=admin \
		-e OC_ADMIN_PASSWORD=password \
		juanbaez/smashbox-docker:latest \
		lib/test_basicSync.py

This runs:

	bin/smash lib/test_basicSync.py

To run all test suits with all test sets replace `lib/test_basicSync.py` by `-a lib/`.

## Environment variables

Following environment variables are supported

* `OC_ACCOUNT_PASSWORD` (default: `qwertzuiopüasdfghjk`) this setting will provide the password that will be used for all created users
* `OC_SERVER` IP address of the ownCloud instance
* `OC_ROOT` the webroot of the ownCloud instance (i.e. set this to `owncloud` for an instance at `http://123.45.67.89/owncloud/`)
* `OC_ADMIN_USER` (default: `at_admin`) username of the admin user of that instance
* `OC_ADMIN_PASSWORD` (default: `admin`) password of the admin user of that instance
