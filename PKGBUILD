# Maintainer: AndyRTR <andyrtr@archlinux.org>
# Contributor: Xavier Devlamynck <magicrhesus@ouranos.be>

pkgname=libxfce4ui
pkgver=4.7.3
pkgrel=1
pkgdesc="share commonly used Xfce widgets among the Xfce applicationsa freedesktop.org compliant ui implementation for Xfce (Development Version)
arch=('i686' 'x86_64')
license=('GPL2')
url="http://www.xfce.org/"
groups=('xfce4')
options=('!libtool')
source=(http://archive.xfce.org/src/xfce/libxfce4ui/4.7/${pkgname}-${pkgver}.tar.bz2)
md5sums=('919ebc5891a4403fa352f65e42ee401f')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  ./configure --prefix=/usr --sysconfdir=/etc --libexecdir=/usr/lib \
    --localstatedir=/var --disable-static --enable-maintainer-mode
  make
}

package() {
  cd ${srcdir}/${pkgname}-${pkgver}
  make DESTDIR=${pkgdir} install
}
