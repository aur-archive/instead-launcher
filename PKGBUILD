# Contributor: Peter Kosyh <p.kosyhgmail.com>
pkgname=instead-launcher
pkgver=0.6.1
pkgrel=2
pkgdesc="launcher and games downloader for INSTEAD quest interpreter"
arch=('i686' 'x86_64')
url="http://instead-launcher.googlecode.com/"
license=('GPL')

depends=('qt' 'instead')
makedepends=('sed')

source=(http://instead-launcher.googlecode.com/files/instead-launcher_$pkgver.tar.gz)
md5sums=(b2136e535dbb77eacb79e3357dc2a173)

build() {
cd $startdir/src/instead-launcher-$pkgver
cat platform.cpp | sed -e 's|/usr/local/bin/sdl-instead|/usr/bin/sdl-instead|g' > platform.cpp.new
mv -f platform.cpp.new platform.cpp
qmake PREFIX=/usr || return 1.
make INSTALL_ROOT=${startdir}/pkg install
}
