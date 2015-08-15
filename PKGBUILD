# Contributor: Alexander Fehr <pizzapunk gmail com>
# Contributor: Ashok Gautham (ScriptDevil) <script_devil@yahoo.com>
# Maintainer: Martynas Januskauskas <martynas@januskauskas.eu>
pkgname=bygfoot
pkgver=2.3.2
pkgrel=3
pkgdesc="Football (a.k.a. soccer) management game"
arch=('i686' 'x86_64')
url="http://www.bygfoot.com/"
license=('GPL')
depends=('gtk2' 'zip' 'unzip')
source=(http://downloads.sourceforge.net/bygfoot/bygfoot-$pkgver.tar.bz2
        bygfoot.desktop)

md5sums=('152c0c729c2b5e4428d32b89edc6dd14'
         'acd86cc1d940a79547899718abc23178')

build() {
  cd $srcdir/bygfoot-$pkgver
  ./configure --prefix=/usr LIBS="-lm" || return 1
  make || return 1
  make DESTDIR=$pkgdir install || return 1

  install -D -m644 support_files/pixmaps/bygfoot_icon.png \
    $startdir/pkg/usr/share/pixmaps/bygfoot.png
  install -D -m644 ../bygfoot.desktop $startdir/pkg/usr/share/applications/bygfoot.desktop
}
