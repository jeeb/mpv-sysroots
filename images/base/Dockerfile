FROM fedora:37

# expected:
# mingw-binutils-generic
# mingw-filesystem-base
# mingw64-binutils
# mingw64-cpp
# mingw64-crt
# mingw64-filesystem
# mingw64-gcc
# mingw64-gcc-c++
# mingw64-headers
# mingw64-libgcc
# mingw64-winpthreads
# mingw64-winpthreads-static

RUN \
	dnf -y update --refresh && \
	dnf -y install \
		autoconf \
		automake \
		clang \
		clang-analyzer \
		curl \
		gcc \
		gcc-c++ \
		git \
		make \
		mingw64-gcc \
		mingw64-gcc-c++ \
		mingw64-winpthreads-static \
		meson \
		nasm \
		ninja-build \
		pkgconf \
		pkgconf-pkg-config && \
	dnf clean all && \
	find /usr/x86_64-w64-mingw32/sys-root/mingw/ -iname '*.dll.a' -delete -print && \
    git config --global user.email "builder@localhost" && \
    git config --global user.name "Builder" && \
    git config --global advice.detachedHead false
