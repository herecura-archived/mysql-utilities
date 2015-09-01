# Maintainer: Raphaël Doursenaud <rdoursenaud@free.fr>
pkgname=mysql-utilities
pkgver=1.5.5
pkgrel=1
pkgdesc="A collection of command-line utilities that are used for maintaining and administering MySQL servers"
arch=('any')
url="http://dev.mysql.com/downloads/tools/utilities/"
license=('GPL')
depends=('python2' 'python2-sphinx' 'python2-jinja' 'python2-mysql-connector')
options=(!emptydirs)
source=(http://cdn.mysql.com/Downloads/MySQLGUITools/$pkgname-$pkgver.tar.gz)
sha256sums=('c320bfbc82844866d4fbe3bfa366e028ff1cff44cd56a5b1a48e875f1cb0db05')

package() {
	cd "$srcdir/$pkgname-$pkgver"
	python2 setup.py install --root="$pkgdir/" --optimize=1

	# Remove files clashing with python2-mysql-connector
	rm -f "$pkgdir/usr/lib/python2.7/site-packages/mysql/__init__.py"
	rm -f "$pkgdir/usr/lib/python2.7/site-packages/mysql/__init__.pyc"
	rm -f "$pkgdir/usr/lib/python2.7/site-packages/mysql/__init__.pyo"
}
