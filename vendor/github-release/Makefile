include ../../tasks/Makefile.package
include ../../tasks/Makefile.apk

# Package details
export VENDOR ?= github-release
# https://github.com/github-release/github-release/releases/download/v0.8.1/darwin-amd64-github-release.bz2
export DOWNLOAD_URL ?= $(PACKAGE_REPO_URL)/releases/download/v$(PACKAGE_VERSION)/$(OS)-$(ARCH)-$(PACKAGE_NAME).bz2
export APK_BUILD_TEMPLATE ?= APKBUILD.github-binary
export APKBUILD_DEPENDS += libc6-compat

install:
	$(call download_binary_bz2)

test:
	$(PACKAGE_EXE) --version
