pkgname=evas_generic_loaders
pkgver=1.17.0
pkgrel=1
pkgdesc="Additional generic loaders for Evas"
arch=('x86_64')
url="http://www.enlightenment.org"
license=('GPL2')
depends=('librsvg' 'poppler' 'libraw' 'libspectre' 'efl')
source=(http://download.enlightenment.org/rel/libs/${pkgname}/${pkgname}-${pkgver}.tar.gz)
md5sums=('e6c619517e64d0596652f075fd5b24fc')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  export CFLAGS="$CFLAGS -fvisibility=hidden"

  ./configure \
    --prefix=/usr \
    --libexecdir=/usr/lib/evas \
    --enable-poppler \
    --enable-spectre \
    --enable-libraw \
    --enable-svg \
    --enable-gstreamer
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}" install
}
