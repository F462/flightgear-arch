# Maintainer: Jake <aur@ja-ke.tech>
# Contributor: Sergej Pupykin <pupykin.s+arch@gmail.com>
# Contributor: William Rea <sillywilly@gmail.com>
# Contributor: Hans Janssen <hans@janserv.xs4all.nl>

pkgname=simgear
pkgver=2018.2.2
_pkgver=${pkgver%.*}
pkgrel=1
pkgdesc="A set of open-source libraries designed to be used as building blocks for quickly assembling 3d simulations, games, and visualization applications."
arch=(x86_64)
depends=('glu' 'glut' 'freealut' 'plib' 'openscenegraph')
makedepends=('boost' 'cmake' 'mesa')
license=("GPL")
url="http://www.flightgear.org/"
options=('makeflags' 'staticlibs')
source=("https://downloads.sourceforge.net/project/flightgear/release-${_pkgver}/${pkgname}-${pkgver}.tar.bz2")
sha256sums=('f61576bc36aae36f350154749df1cee396763604c06b8a71c4b50452d9151ce5')

build() {
  cd "$srcdir"/simgear-$pkgver
  mkdir ../sgbuild && cd ../sgbuild
  cmake -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_INSTALL_LIBDIR=lib -DCMAKE_BUILD_TYPE=Release ../simgear-${pkgver}
  make
}

package() {
  cd "$srcdir"/sgbuild
  make DESTDIR="$pkgdir" install
}
