# Maintainer: Andrew Whatson <whatson@gmail.com>
# Contributor: Jake <aur@ja-ke.tech>
# Contributor: Sergej Pupykin <pupykin.s+arch@gmail.com>
# Contributor: William Rea <sillywilly@gmail.com>
# Contributor: Hans Janssen <hans@janserv.xs4all.nl>

pkgname=simgear
pkgver=2020.3.4
_pkgver=${pkgver%.*}
pkgrel=1
pkgdesc="A set of open-source libraries designed to be used as building blocks for quickly assembling 3d simulations, games, and visualization applications."
arch=('x86_64')
url="http://home.flightgear.org/"
license=('GPL')
depends=('glu' 'glut' 'freealut' 'plib' 'openscenegraph')
makedepends=('boost' 'cmake' 'mesa')
options=('staticlibs')
source=("https://downloads.sourceforge.net/project/flightgear/release-${_pkgver}/${pkgname}-${pkgver}.tar.bz2")
sha256sums=('10d4159d84ae0c6f457b089cba5050a705d7b6ca42f42e19f8c2ed4b69434ad1')

build() {
  mkdir -p "$srcdir"/simgear-build
  cd "$srcdir"/simgear-build
  cmake \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DCMAKE_INSTALL_LIBDIR=lib \
    -DCMAKE_BUILD_TYPE=Release \
    -DENABLE_TESTS=off \
    ../simgear-${pkgver}
  make
}

package() {
  cd "$srcdir"/simgear-build
  make DESTDIR="$pkgdir" install
}
