pkgname=sddm
pkgver=0.9.0
pkgrel=1
pkgdesc="QML based X11 display manager"
arch=('i686' 'x86_64')
url="http://github.com/sddm/sddm"
license=('GPL')
depends=('qt5-declarative')
makedepends=('cmake' 'python-docutils' 'qt5-tools')
conflicts=('lightdm')
install='sddm.install'

source=("https://github.com/sddm/sddm/archive/v${pkgver}.tar.gz")
md5sums=('9cbe192e7fee6a384402d28c0e50c0e2')

build() {
  cd "${pkgname}-${pkgver}"
  mkdir -p build
  cd build
  cmake .. \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_INSTALL_LIBEXECDIR=/usr/lib/sddm \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_MAN_PAGES=ON \
        -DUSE_QT5=true
  make
}

package() {
  cd "${pkgname}-${pkgver}/build" &&
  make DESTDIR="${pkgdir}" install
}

