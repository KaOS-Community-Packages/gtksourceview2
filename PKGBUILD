
pkgname=gtksourceview2
pkgver=2.10.5
pkgrel=2
pkgdesc="A text widget adding syntax highlighting and more to GNOME"
arch=('x86_64')
license=('GPL')
depends=('gtk2>=2.22.0' 'libxml2>=2.7.7')
makedepends=('intltool' 'pkg-config')
url="http://www.gnome.org"
source=(http://ftp.gnome.org/pub/gnome/sources/gtksourceview/2.10/gtksourceview-${pkgver}.tar.bz2)
sha256sums=('c585773743b1df8a04b1be7f7d90eecdf22681490d6810be54c81a7ae152191e')

build() {
  cd "${srcdir}/gtksourceview-${pkgver}"
  sed -i 's#python#python2#' gtksourceview/language-specs/convert.py
  ./configure --prefix=/usr --sysconfdir=/etc \
      --localstatedir=/var --disable-static
  make
}

package() {
  cd "${srcdir}/gtksourceview-${pkgver}"
  make DESTDIR="${pkgdir}" install
}
