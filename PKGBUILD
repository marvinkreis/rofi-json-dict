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
    cd "$srcdir/rofi-plugins"
    autoreconf -i
    ./configure
    make
}

package() {
    cd "$srcdir/rofi-plugins"
    make DESTDIR="$pkgdir" PREFIX=/usr install
}
