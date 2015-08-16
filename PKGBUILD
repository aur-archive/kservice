# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kservice
pkgver=4.99.0
pkgrel=1
pkgdesc='KService'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/kservice'
license=('LGPL')
depends=('ki18n' 'kconfig' 'kcrash' 'kdbusaddons')
makedepends=('extra-cmake-modules' 'kdoctools')
groups=('kf5')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('9679f8020d9ed4500de27c2c76a0d434')

prepare() {
  mkdir -p build
}

build() {
  export XDG_DATA_DIRS="/opt/kf5/share:$XDG_DATA_DIRS"

  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
#    -DSYSCONF_INSTALL_DIR=/etc
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
