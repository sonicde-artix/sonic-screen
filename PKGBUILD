# Maintainer: callmetango
# Contributor: artist <artist@artixlinux.org>

pkgname=sonic-screen
pkgver=6.6.5
pkgrel=2
pkgdesc='Screen management software for SonicDE Workspaces'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-screen'
license=(LGPL-2.0-or-later)
depends=(gcc-libs
         glibc
         kcmutils
         kconfig
         kcrash
         kdbusaddons
         ki18n
         kimageformats
         kitemmodels
         ksvg
         libx11
         libxcb
         libxi
         plasma5support
         qt6-base
         qt6-declarative
         sonic-frameworks-core-addons
         sonic-frameworks-quick-ui
         sonic-frameworks-windowsystem
         sonic-interface-libraries
         sonic-screen-library)
makedepends=(extra-cmake-modules)
groups=(sonicde)
conflicts=(kscreen)
provides=(kscreen)
replaces=(kscreen)
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('c32c825529a69b30d81beeccce834a48bcc8e922401473210d922024693c6d1a')

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
