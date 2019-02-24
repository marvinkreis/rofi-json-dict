pkgname=rofi-json-dict
pkgver=0.0.2
pkgrel=1
pkgdesc="Plugin to use rofi as a dictionary"
url="https://github.com/marvinkreis/${pkgname}"
arch=("i686" "x86_64")
license=("MIT")
depends=("rofi")
makedepends=("git")

source=("git://github.com/marvinkreis/${pkgname}.git")
md5sums=("SKIP")

build() {
    cd "${srcdir}/${pkgname}"
    autoreconf --install
    ./configure
    make
}

package() {
    cd "${srcdir}/${pkgname}"
    make DESTDIR="$pkgdir" PREFIX=/usr install
}
