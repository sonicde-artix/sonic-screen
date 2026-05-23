# Maintainer: artist for Artix Linux

pkgname=sonic-screen
pkgver=6.6.5
pkgrel=1
_commit="a971755f028bd31573b4a6c7d2c260f344627012"
pkgdesc='Screen management software for SonicDE Workspaces'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-screen'
license=(LGPL-2.0-or-later)
depends=(gcc-libs
         glibc
         kcmutils
         kconfig
         sonic-frameworks-core-addons
         kcrash
         kdbusaddons
         ki18n
         kimageformats
         sonic-frameworks-quick-ui
         kitemmodels
         ksvg
         libx11
         libxcb
         libxi
         plasma5support
         sonic-frameworks-windowsystem
         sonic-interface-libraries
         sonic-screen-library
         qt6-base
         qt6-declarative)
makedepends=(extra-cmake-modules)
groups=(sonicde)
conflicts=(kscreen)
provides=(kscreen)
replaces=(kscreen)
makedepends+=(git)
source=("$pkgname-$pkgver::git+$url.git#commit=$_commit")

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

sha256sums=('64c705e01dd0a3a20e05bffbb511a3920b3040760df673e49fe081b069f42e72')

