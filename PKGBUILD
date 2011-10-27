# Maintainer: Evangelos Foutras <evangelos@foutrelis.com>
# Contributor: Xavier Devlamynck <magicrhesus@ouranos.be>

pkgname=libxfce4ui
pkgver=4.8.0
pkgrel=3
pkgdesc="Commonly used Xfce widgets among Xfce applications"
arch=('i686' 'x86_64')
url="http://www.xfce.org/"
license=('GPL2')
depends=('libxfce4util' 'gtk2' 'xfconf' 'libsm' 'startup-notification')
makedepends=('intltool' 'gtk-doc' 'glade')
optdepends=('glade: for using the included glade module')
#replaces=('libxfcegui4') - later when all is ported
options=('!libtool')
source=(http://archive.xfce.org/src/xfce/$pkgname/4.8/$pkgname-$pkgver.tar.bz2)
sha1sums=('107f9d8e3e583f3cf5330074e89ea72eb2a82888')

build() {
  cd "$srcdir/$pkgname-$pkgver"

  ./configure --prefix=/usr \
    --sysconfdir=/etc \
    --libexecdir=/usr/lib \
    --localstatedir=/var \
    --disable-static \
    --enable-gtk-doc \
    --disable-debug
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make DESTDIR="$pkgdir" install
}

# vim:set ts=2 sw=2 et:
