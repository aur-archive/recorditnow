# Mantainer: Yichao Yu <yyc1992@gmail.com>
# Contributor: Weng Xuetian <wengxt@gmail.com>
# Contributor: Adrià Arrufat <swiftscythe@gmail.com>
# Contributor: Callea Gaetano Andrea <callea:gaetano:andrea/gmail:com>

pkgname=recorditnow
pkgver=0.8.1
pkgrel=4
pkgdesc="A plugin based desktop recorder for KDE SC 4"
arch=('i686' 'x86_64')
url="http://kde-apps.org/content/show.php/RecordItNow?content=114610"
license=('GPL')
depends=('kdebase-runtime' 'recordmydesktop' 'ffmpeg')
makedepends=('cmake' 'automoc4')
optdepends=('mencoder: for mencoder encoder plugin')
provides=('recorditnow' 'joschy')
conflicts=('joschy-git')
source=(
  "http://downloads.sourceforge.net/project/recorditnow/${pkgname}-${pkgver}.tar.bz2"
  "cmake.patch")
md5sums=('6619b4048545adbab1d13a790189e80f'
         '74ea0ababc2291e2a62e5d045c62616a')

build() {
  cd "${srcdir}/$pkgname-$pkgver/"
  patch -i "${srcdir}/cmake.patch" -p0 || return 1
  mkdir -p build
  cd build
  cmake -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release \
    -DLINGUAS="de hu cs pt_BR fr it" ..
  make
  make "DESTDIR=${pkgdir}" install
}
