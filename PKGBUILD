pkgname=dwm
pkgver=6.5
pkgrel=1
pkgdesc="A dynamic window manager for X (Forked Version)"
url="https://github.com/yourusername/dwm"
arch=('i686' 'x86_64' 'arm' 'armv7h' 'armv6h' 'aarch64')
license=('MIT')
depends=('libx11' 'libxinerama' 'libxft' 'freetype2')
source=("git+https://github.com/EilonIssac/dwm-SimpleOS.git#branch=SimpleOS"
        "dwm.desktop"
        "config.h")
sha256sums=('SKIP'
            'SKIP'
            'SKIP')

prepare() {
  cd "$srcdir"/dwm-SimpleOS
}

build() {
  cd "$srcdir"/dwm-SimpleOS
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11 FREETYPEINC=/usr/include/freetype2
}

package() {
  cd "$srcdir"/dwm-SimpleOS
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  install -Dm644 README "$pkgdir/usr/share/doc/$pkgname/README"
  install -Dm644 "$srcdir/dwm.desktop" "$pkgdir/usr/share/xsessions/dwm.desktop"
}
