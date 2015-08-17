# Contributor: Antonio Rojas

pkgname=oxygen
pkgver=5.0.2
pkgrel=1
pkgdesc='KDE Oxygen style'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/kde/workspace/oxygen'
license=('LGPL')
depends=('frameworkintegration' 'kwin')
makedepends=('extra-cmake-modules' 'kdoctools')
conflicts=('kdebase-workspace')
source=("http://download.kde.org/stable/plasma/$pkgver/$pkgname-$pkgver.tar.xz")
md5sums=('b9e4e84e68e7b69babd899725ea8bb94')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../$pkgname-$pkgver \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DLIB_INSTALL_DIR=lib \
    -DLOCALE_INSTALL_DIR=share/locale/kf5 \
    -DKDE_INSTALL_USE_QT_SYS_PATHS=ON
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
