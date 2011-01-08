# Maintainer: AndyRTR <andyrtr@archlinux.org>
# Contributor: Xavier Devlamynck <magicrhesus@ouranos.be>

pkgname=libxfce4ui
pkgver=4.7.6
pkgrel=2
pkgdesc="share commonly used Xfce widgets among the Xfce applications"
arch=('i686' 'x86_64')
license=('GPL2')
url="http://www.xfce.org/"
groups=('xfce4')
depends=('libxfce4util>=4.7.3' 'gtk2' "xfconf>=4.7.3" 'startup-notification') 
makedepends=('intltool' 'gtk-doc' 'glade')
optdepends=('glade: for using the included glade module')
#replaces=('libxfcegui4')
options=('!libtool')
source=(http://archive.xfce.org/src/xfce/libxfce4ui/4.7/${pkgname}-${pkgver}.tar.bz2)
md5sums=('beccb7eb6fb36bec38b5d140ed42480e')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
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
  cd ${srcdir}/${pkgname}-${pkgver}
  make DESTDIR=${pkgdir} install
}
