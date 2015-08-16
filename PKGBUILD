# Maintainer: Antonio Rojas 

pkgname=libkpeople-git
pkgver=r933.88f8e64
pkgrel=1
pkgdesc='A library that provides access to all contacts and the people who hold them'
arch=('i686' 'x86_64')
url='http://community.kde.org/KTp/libkpeople'
license=('LGPL')
depends=('baloo-frameworks')
makedepends=('extra-cmake-modules' 'git' 'python')
replaces=('libkpeople-frameworks-git')
source=("git://anongit.kde.org/libkpeople.git")
sha256sums=('SKIP')

pkgver() {
  cd libkpeople
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
  mkdir -p build
}

build() { 
  cd build
  cmake ../libkpeople \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DCMAKE_BUILD_TYPE=Release \
    -DLIB_INSTALL_DIR=lib \
    -DKDE_INSTALL_USE_QT_SYS_PATHS=ON
  make
}

package() {
  cd build
  make DESTDIR="$pkgdir" install
}
