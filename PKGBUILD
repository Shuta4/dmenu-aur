# Maintainer: Shuta4 <shuta4@proton.me>

_pkgname=dmenu
pkgname="s4-$_pkgname"
pkgver=5.0
pkgrel=1
pkgdesc="Generic menu for X custom build"
url="https://github.com/Shuta4/dmenu"
arch=('i686' 'x86_64')
license=('MIT')
options=(zipman)
depends=(
	coreutils
	fontconfig
	freetype2
	glibc
	libfontconfig.so
	libx11
	libxft
	libxinerama
	sh
)
source=("https://github.com/Shuta4/$_pkgname/archive/refs/tags/$pkgver-$pkgrel.tar.gz")
sha256sums=('680cf1156b33ccd794db7dac9cf91039f7f211bb48eb9d20329c15194e6d444d')

provides=("${_pkgname}")
conflicts=("${_pkgname}")

build() {
  cd "$srcdir/$_pkgname-$pkgver-$pkgrel"
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11 FREETYPEINC=/usr/include/freetype2
}

package() {
  cd "$srcdir/$_pkgname-$pkgver-$pkgrel"
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$_pkgname/LICENSE"
  install -Dm644 README.md "$pkgdir/usr/share/doc/$_pkgname/README.md"
}
