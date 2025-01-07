# Debian Packaging of flask-session for Wazo

This repository contains the packaging information for
[python-flask-session](https://github.com/fengsp/flask-session).

## Reason

* Not packaged by Debian Buster
* Needed by wazo-ui

## Building a New Version

To build a new version of python-flask-session for Wazo.

* Set the new version in the `VERSION` file.
* Add a changelog entry entry in `debian/changelog`
* Push to the master branch

[Jenkins](https://jenkins.wazo.community) will then retrieve and build the new version.

### Changelog Version Number

The version in the changelog MUST have the following format:

`<upstream_version>-1~wazo<1..n>`

## Building Locally

To build on a test environment before submitting a change to production the following procedure can be used.

```sh
make -f debian/rules get-orig-source
tar -xvf ../wazo-python-flask-session-packaging_*.orig.tar.gz --strip 1
dpkg-buildpackage -us -uc
```

The `.deb` will be located in the parent directory.
