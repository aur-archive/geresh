# Maintainer: Yoel Lion <yoel3ster at gmail dot com>

pkgname=geresh
pkgver=20120925
pkgrel=1
pkgdesc="A simple bidi-enabled text editor (git version)"
arch=('i686' 'x86_64')
url="http://www.typo.co.il/~mooffie/geresh/"
license=('GPLv2')
depends=('fribidi' 'ncurses' 'libstdc++5')

build() {
	msg "Downloading..."
	curl -OR http://gitorious.org/geresh/geresh/archive-tarball/master
	bsdtar -x -f master
	msg "Packaging..."

	cd "$srcdir/$pkgname-$pkgname"
	sed -i '5cAC_INIT([geresh], [0.6.4])' configure.ac
	autoconf
	autoreconf -i
	export LDFLAGS="$LDFLAGS -lm"
	./configure --prefix=/usr
	make
 
}

package() {
	cd "$srcdir/$pkgname-$pkgname"
	make DESTDIR="${pkgdir}" install
} 
