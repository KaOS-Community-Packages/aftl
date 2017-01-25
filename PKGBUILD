pkgname=aftl
pkgver=3.0.70
pkgrel=1
epoch=1
_commit=fde9cbb6887da15c3bc2ccf1884ceb873067d79a
pkgdesc="Android file transfer for linux is a mtp client for android devices"
url="https://github.com/whoozle/android-file-transfer-linux"
license=('GPL')
arch=('x86_64')
depends=('readline' 'qt5-base' 'fuse')
makedepends=('cmake')
source=("aftl.zip::https://github.com/whoozle/android-file-transfer-linux/archive/{$_commit}.zip")
md5sums=('e8ac764433f8e25b2634d4fd367ee951')

prepare() {
    cd "${srcdir}/android-file-transfer-linux-${_commit}"
    mkdir -p build
}

build() {
    cd "${srcdir}/android-file-transfer-linux-${_commit}/build"
    cmake .. -DCMAKE_INSTALL_PREFIX=/usr
    make
}

package() {
    cd "${srcdir}/android-file-transfer-linux-${_commit}/build"
    make DESTDIR="${pkgdir}/" install
}
