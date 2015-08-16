# $Id: PKGBUILD 79480 2012-11-06 03:41:12Z bgyorgy $
# Maintainer: Balló György <ballogyor+arch at gmail dot com>

pkgname=nautilus-sound-converter
pkgver=3.0.2
pkgrel=2
pkgdesc="Nautilus extension to convert audio files formats"
arch=('i686' 'x86_64')
url="http://code.google.com/p/nautilus-sound-converter/"
license=('GPL')
depends=('nautilus' 'libgnome-media-profiles')
makedepends=('intltool')
optdepends=('gstreamer0.10-good-plugins: Extra media codecs'
            'gstreamer0.10-ugly-plugins: Extra media codecs'
            'gstreamer0.10-bad-plugins: Extra media codecs'
            'gstreamer0.10-ffmpeg: Extra media codecs')
conflicts=('totem>=3.6.0')
options=('!libtool')
install=$pkgname.install
source=(http://nautilus-sound-converter.googlecode.com/files/$pkgname-$pkgver.tar.xz)
sha1sums=('f0799af3c7f14e2cd4cf70499d9bde07ec4ab89d')

build() {
  cd "$srcdir/$pkgname-$pkgver"

  ./configure --prefix=/usr --sysconfdir=/etc --localstatedir=/var \
              --disable-static --disable-schemas-install \
              --with-gconf-schema-file-dir=/usr/share/gconf/schemas
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"

  make DESTDIR="$pkgdir/" install
}
