# SPDX-License-Identifier: Apache-2.0
# Copyright 2018 Gliim LLC. 
# Licensed under Apache License v2. See LICENSE file.
# On the web http://golf-lang.com/ - this file is part of Golf framework.

# Build locally: makepkg --noconfirm -s
# Check this file: namcap PKGBUILD
# Run installer: sudo pacman -U --noconfirm <pkg.tar.gz file>

# Maintainer: Gliim LLC <team@golf-lang.com>
pkgname=golf
pkgver=335
pkgrel=0
epoch=
pkgdesc="Programming language and application server for building and running web services and web applications. High performance and memory-safe."
arch=("x86_64")
url="https://golf-lang.com"
license=('Apache-2.0')
groups=()
#NOTE: when depends change, makepkg --printsrcinfo >.SRCINFO must run to refresh .SRCINFO !!
depends=(make gcc openssl curl 'mariadb-connector-c' fcgi 'postgresql-libs' sqlite3 pcre2 libxml2)
makedepends=()
checkdepends=()
optdepends=()
provides=(golf)
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=("${pkgname}-${pkgver}.tar.gz::https://github.com/golf-lang/golf/archive/refs/tags/${pkgver}.tar.gz")
        
noextract=()
md5sums=(SKIP)
validpgpkeys=()

prepare() {
	tar xvfz ${pkgname}-${pkgver}.tar.gz 
}

build() {
	cd "${pkgname}-${pkgver}"
	make DESTDIR="$pkgdir/" clean
	make DESTDIR="$pkgdir/"
}

check() {
	cd "${pkgname}-${pkgver}"
}

package() {
	cd "${pkgname}-${pkgver}"
	make DESTDIR="$pkgdir/" install
}
