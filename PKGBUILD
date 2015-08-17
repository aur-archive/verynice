# Maintainer: Lara Maia <lara@craft.net.br>
# Contributor: Lucas Salies Brum <lucas@archlinux.com.br>

pkgname=verynice
pkgver=1.1
pkgrel=14
pkgdesc="A tool for dynamically adjusting the nice level of processes under UNIX-like operating systems."
url="http://thermal.cnde.iastate.edu/~sdh4/verynice/"
arch=('i686' 'x86_64')
license=('GPL')
depends=('bash')
backup=("etc/$pkgname.conf")

source=("http://fossies.org/linux/misc/old/$pkgname-$pkgver.tar.gz"
	    "$pkgname.service")

md5sums=('fb00b79779a30df2c03916181c873545'
         'dd2aee4e833c9f668e10c894c6c4d189')

build() {
	cd "$srcdir"/$pkgname/
	
	make
}

package() {
	cd "$srcdir"
	
	install -D -m755 $pkgname/$pkgname      "$pkgdir"/usr/bin/$pkgname
	install -D -m644 $pkgname/$pkgname.conf "$pkgdir"/etc/$pkgname.conf
	install -D -m755 $pkgname.service       "$pkgdir"/usr/lib/systemd/system/$pkgname.service
}
