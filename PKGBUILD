# Maintainer: <n17ikh@gmail.com>
pkgname=luksipc
pkgver=0.01
pkgrel=2
pkgdesc="A tool to convert unencrypted block devices to encrypted LUKS devices in-place"
arch=(any)
url="http://www.johannes-bauer.com/linux/luksipc"
license=('GPL3')
source=($url/$pkgname-$pkgver.tar.gz return_code.patch)
md5sums=('8a61e207dfd020f634ede641bc57fe63'
         '53bc909090376e830c3de70136b2e29c')

build() {
	cd "$srcdir/$pkgname-$pkgver"
	patch -p1 < $srcdir/return_code.patch
	make all
}

package() {
	cd "$srcdir/$pkgname-$pkgver"
	install -Dm 755 $pkgname $pkgdir/usr/bin/$pkgname
}
