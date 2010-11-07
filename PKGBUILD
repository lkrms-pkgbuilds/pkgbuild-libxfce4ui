# Maintainer: AndyRTR <andyrtr@archlinux.org>
# Contributor: Xavier Devlamynck <magicrhesus@ouranos.be>

pkgname=libxfce4ui
pkgver=4.7.4
pkgrel=1
pkgdesc="share commonly used Xfce widgets among the Xfce applicationsa freedesktop.org compliant ui implementation for Xfce (Development Version)"
arch=('i686' 'x86_64')
license=('GPL2')
url="http://www.xfce.org/"
groups=('xfce4')
depends=('libxfce4util>=4.7.3' 'gtk2' "xfconf>=4.7.3" 'startup-notification' 'glade')
makedepends=('intltool' 'gtk-doc' )
options=('!libtool')
source=(http://archive.xfce.org/src/xfce/libxfce4ui/4.7/${pkgname}-${pkgver}.tar.bz2)
md5sums=('4d3cc02c6b09552b940d5d09245e8934')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  ./configure --prefix=/usr --sysconfdir=/etc --libexecdir=/usr/lib \
    --localstatedir=/var --disable-static # --enable-maintainer-mode
  make
}

package() {
  cd ${srcdir}/${pkgname}-${pkgver}
  make DESTDIR=${pkgdir} install
}
