# Maintainer: Raphaël Doursenaud <rdoursenaud@free.fr>
pkgname=mysql-utilities
pkgver=1.6.5
pkgrel=1
pkgdesc="A collection of command-line utilities that are used for maintaining and administering MySQL servers"
arch=('any')
url="http://dev.mysql.com/downloads/tools/utilities/"
license=('GPL')
depends=('python2' 'python2-sphinx' 'python2-jinja' 'python2-mysql-connector')
options=(!emptydirs)
source=(http://cdn.mysql.com/Downloads/MySQLGUITools/$pkgname-$pkgver.tar.gz)
sha256sums=('03272b103d66f9cf8bcd4dcf233b04c95ddba8ef078502bcf178dc1b709cbed4')

package() {
	cd "$srcdir/$pkgname-$pkgver"
	python2 setup.py install --root="$pkgdir/" --optimize=1

	# Remove files clashing with python2-mysql-connector
	rm -f "$pkgdir/usr/lib/python2.7/site-packages/mysql/__init__.py"
	rm -f "$pkgdir/usr/lib/python2.7/site-packages/mysql/__init__.pyc"
	rm -f "$pkgdir/usr/lib/python2.7/site-packages/mysql/__init__.pyo"
}
