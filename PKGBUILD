# Maintainer: Evangelos Foutras <evangelos@foutrelis.com>
# Contributor: Xavier Devlamynck <magicrhesus@ouranos.be>

pkgname=libxfce4ui
pkgver=4.12.0
pkgrel=1
pkgdesc="Commonly used Xfce widgets among Xfce applications"
arch=('i686' 'x86_64')
url="http://www.xfce.org/"
license=('GPL2')
depends=('libxfce4util' 'gtk2' 'gtk3' 'xfconf' 'libsm' 'startup-notification'
         'hicolor-icon-theme')
makedepends=('intltool' 'gtk-doc')
#replaces=('libxfcegui4') - later when all is ported
install=$pkgname.install
source=(http://archive.xfce.org/src/xfce/$pkgname/${pkgver%.*}/$pkgname-$pkgver.tar.bz2)
sha256sums=('011d9532337a8d0c4d6d2c4dfc854b4f298dbad0e9513b3495a573673b863987')

build() {
  cd "$srcdir/$pkgname-$pkgver"

  ./configure \
    --prefix=/usr \
    --sysconfdir=/etc \
    --libexecdir=/usr/lib \
    --localstatedir=/var \
    --disable-static \
    --enable-gtk-doc \
    --disable-debug \
    --with-vendor-info='Arch Linux'
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make DESTDIR="$pkgdir" install
}

# vim:set ts=2 sw=2 et:
