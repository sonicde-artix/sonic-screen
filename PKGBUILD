# Maintainer: artist for Sonic-DE

pkgname=sonic-screen
pkgver=6.6.3
_dirver=$(echo $pkgver | cut -d. -f1-3)
pkgrel=3
pkgdesc='Sonic-screen is the screen management software for SonicDE Workspaces'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-screen'
license=(LGPL-2.0-or-later)
depends=(gcc-libs
         glibc
         kcmutils
         kconfig
         kcoreaddons
         kcrash
         kdbusaddons
         ki18n
         kimageformats
         kirigami
         kitemmodels
         ksvg
         kwindowsystem
         layer-shell-qt
         sonic-screen-library
         libx11
         libxcb
         libxi
         libplasma
         plasma5support
         qt6-base
         qt6-declarative)
makedepends=(extra-cmake-modules)
groups=(sonicde)
conflicts=(kscreen)
provides=(kscreen)
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/$_dirver.tar.gz")

build() {
  cmake -B build  -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF \
    -DCMAKE_INSTALL_LIBEXECDIR=lib
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build

  rm -r $pkgdir/usr/lib/systemd
}

sha256sums=('cb16a5eda5d382a709023c352acec58d7606cb23490c57fe7d4e1ead395347ce')

