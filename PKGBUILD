# Maintainer: AndyRTR <andyrtr@archlinux.org>
# Contributor: Xavier Devlamynck <magicrhesus@ouranos.be>

pkgname=libxfce4ui
pkgver=4.8.0
pkgrel=3
pkgdesc="share commonly used Xfce widgets among the Xfce applications"
arch=('i686' 'x86_64')
license=('GPL2')
url="http://www.xfce.org/"
depends=('libxfce4util>=4.8.0' 'gtk2' "xfconf>=4.8.0" 'libsm' 'startup-notification') 
makedepends=('intltool' 'gtk-doc' 'glade')
optdepends=('glade: for using the included glade module')
#replaces=('libxfcegui4') - later when all is ported
options=('!libtool')
source=(http://archive.xfce.org/src/xfce/libxfce4ui/4.8/${pkgname}-${pkgver}.tar.bz2)
md5sums=('df9acb3328dff905bd0777b84532b69f')

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
