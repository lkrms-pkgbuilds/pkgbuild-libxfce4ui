# Maintainer: Luke Arms <luke@arms.to>
# Contributor: Evangelos Foutras <foutrelis@archlinux.org>
# Contributor: Robin Candau <antiz@archlinux.org>
# Contributor: Xavier Devlamynck <magicrhesus@ouranos.be>

pkgname=libxfce4ui
pkgver=4.18.6
pkgrel=3
pkgdesc="Widgets library for the Xfce desktop environment"
arch=('x86_64')
url="https://docs.xfce.org/xfce/libxfce4ui/start"
license=('GPL-2.0-only')
depends=('libxfce4util' 'gtk3' 'xfconf' 'libsm' 'startup-notification'
         'libgtop' 'libepoxy' 'hicolor-icon-theme')
makedepends=('git' 'glib2-devel' 'intltool' 'gobject-introspection' 'vala' 'xfce4-dev-tools')
source=("git+https://gitlab.xfce.org/xfce/libxfce4ui.git#tag=$pkgname-$pkgver"
        0001-add-xfce_reset_screen_saver.patch)
sha256sums=('ed51a4cffc40dc2688c949b87b55b0aef916f18c39f90565068fa0a9b2c366e3'
            '62992423b0feb9be3e8950d2dcb257f4d6e0e16af688438a8177ac6d355da2b7')

prepare() {
  cd $pkgname
  patch -p1 <"$srcdir/0001-add-xfce_reset_screen_saver.patch"
  ./autogen.sh \
    --build=$CBUILD \
    --host=$CHOST \
    --target=$CTARGET \
    --prefix=/usr \
    --sysconfdir=/etc \
    --localstatedir=/var \
    --disable-debug \
    --enable-gtk-doc \
    --with-vendor-info='Arch Linux'
}

build() {
  cd $pkgname
  make
}

check() {
  cd $pkgname
  make check
}

package() {
  cd $pkgname
  make DESTDIR="$pkgdir" install
}

# vim:set ts=2 sw=2 et:
