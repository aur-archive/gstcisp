# Contributor: Bill Zhechuan Chen <chen.bill.bill(at)gmail.com> 

pkgname=gstcisp
pkgver=1.0
pkgrel=1
pkgdesc="gSTC-ISP is used to program the STC89C52RC by serial port in Linux"
arch=(x86_64 i686)
url="http://gstcisp.sourceforge.net/"
license=('GPL')
source=(http://sourceforge.net/projects/gstcisp/files/gSTC-ISP_v"$pkgver".tar.gz)
depends=("vte" "gtk2")
makedepends=("gcc")
md5sums=(c9a189fae993e0cb0efc30968c07c444)

build() {
  cd "$srcdir/gSTC-ISP/src"
  cp main.c main.c.bak
  sed -i 's/<vte\//<vte-0.0\/vte\//g' main.c
  sed -i 's/<gtk\//<gtk-2.0\/gtk\//g' main.c
  
  cd "$srcdir/gSTC-ISP/"
  ./configure --prefix=/usr
  make
}

package() {
  cd "$srcdir/gSTC-ISP"

  make DESTDIR="$pkgdir/" install
}
