pkgname=aftl
pkgver=3.1.70.fde9cbb
pkgrel=1
pkgdesc="Android file transfer for linux is a mtp client for android devices"
url="https://github.com/whoozle/android-file-transfer-linux"
license=('GPL')
arch=('x86_64')
depends=('readline' 'qt5-base' 'fuse')
makedepends=('cmake' 'git')
source=('git+https://github.com/whoozle/android-file-transfer-linux.git#commit=fde9cbb6887da15c3bc2ccf1884ceb873067d79a')
md5sums=('SKIP')

prepare() {
	cd "${srcdir}/android-file-transfer-linux"
	mkdir build
}

build() {
    cd "${srcdir}/android-file-transfer-linux/build"
	cmake ..
	make
}

package() {
    cd "${srcdir}/android-file-transfer-linux/build"
	make DESTDIR="${pkgdir}/" install
}
