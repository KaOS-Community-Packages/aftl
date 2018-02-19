pkgname=aftl
_pkgfullname=android-file-transfer-linux
pkgver=3.2
pkgrel=1
pkgdesc="Android file transfer for linux is a mtp client for android devices"
url="https://github.com/whoozle/${_pkgfullname}"
license=('GPL')
arch=('x86_64')
depends=(
    'fuse'
    'gcc'
    'glibc'
    'imagemagick'
    'libusb'
    'linux-api-headers'
    'qt5-base'
    'readline'
    'vc'
)
makedepends=(
    'cmake'
    'make'
)
source=("${pkgname}.zip::${url}/archive/v${pkgver}.zip")
md5sums=('1528580e469508a89619113d49fa8cc5')

prepare() {
    cd "${srcdir}/${_pkgfullname}-${pkgver}"
    mkdir -p build
}

build() {
    cd "${srcdir}/${_pkgfullname}-${pkgver}/build"
    cmake .. -DCMAKE_INSTALL_PREFIX=/usr
    make
}

package() {
    cd "${srcdir}/${_pkgfullname}-${pkgver}/build"
    make DESTDIR="${pkgdir}" install
}
