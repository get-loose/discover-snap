# Maintainer: LechTheMitch <ogamal523 at gmail dot com>
# Contributor: tristanrw <N/A>
# Contributor: RTRT <nobody>
# Contributor: Blutkoete <tobias dot borgert at gmail dot com>
# Contributor: 1Conan <me at 1conan dot com>
# Contributor: Mitchell Renouf <mitchellarenouf at gmail dot com> 
# (discover in Extra) Maintainer: Antonio Rojas <arojas at archlinux dot org> 

_pkgname=discover
pkgname=discover-snap
pkgver=6.3.4
_dirver=$(echo $pkgver | cut -d. -f1-3)
pkgrel=1
pkgdesc='KDE and Plasma resources management GUI (with snap backend enabled)'
arch=(x86_64)
url='https://kde.org/plasma-desktop/'
license=(LGPL-2.0-or-later)
conflicts=(discover)
provides=(discover)
depends=(appstream-qt
         archlinux-appstream-data
         attica
         discount
         gcc-libs
         glib2
         glibc
         kcmutils
         kconfig
         kcoreaddons
         kcrash
         kdbusaddons
         ki18n
         kiconthemes
         kidletime
         kio
         kirigami
         kirigami-addons
         kjobwidgets
         knewstuff
         knotifications
         kservice
         kstatusnotifieritem
         kuserfeedback
         kwidgetsaddons
         kwindowsystem
         purpose
         qcoro-qt6
         qt6-base
         qt6-declarative
         qt6-webview
         snapd
         snapd-glib)
makedepends=(extra-cmake-modules
             flatpak
             fwupd
             packagekit-qt6)
optdepends=('flatpak: Flatpak packages support'
            'fwupd: firmware update support'
            'packagekit-qt6: to manage packages from Arch Linux repositories (not recommended, use at your own risk)')
source=(https://download.kde.org/stable/plasma/$_dirver/$_pkgname-$pkgver.tar.xz)
sha256sums=('2a18caed673493cbeb840aa166626d4283272c97578af0bf67e8887b672cf3d8')

build() {
  cmake -B build -S $_pkgname-$pkgver \
    -DCMAKE_INSTALL_LIBEXECDIR=lib \
    -DBUILD_TESTING=OFF \
    -DBUILD_SnapBackend=ON \
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
