## Package - gh
include ../../tasks/Makefile.package
include ../../tasks/Makefile.apk

export VENDOR = cli
export PACKAGE_NAME = gh
export PACKAGE_REPO_NAME = cli
export DOWNLOAD_URL ?= $(PACKAGE_REPO_URL)/releases/download/v$(PACKAGE_VERSION)/$(PACKAGE_NAME)_$(PACKAGE_VERSION)_$(OS)_$(ARCH).tar.gz
export APK_BUILD_TEMPLATE ?= APKBUILD.github-binary

## Uncomment only if you need additional libraries
export APKBUILD_DEPENDS += libc6-compat musl

install:
	$(call download_tarball)

test:
	$(PACKAGE_EXE) --version

## This may be required for apk building and varies from package to package
# Custom post-package processing (Note the double colon to append to current inherited package/prepare task)
package/prepare::
	cp src/gh_$(PACKAGE_VERSION)_$(OS)_$(ARCH)/bin/$(PACKAGE_EXE) src
