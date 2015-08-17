# Maintainer: Francois Boulogne <fboulogne at april dot org>

pkgname=python-html2text
pkgver=2014.9.25
pkgrel=2
pkgdesc="Converts a page of HTML into clean, easy-to-read plain ASCII text."
arch=('any')
url="https://github.com/Alir3z4/html2text/"
license=('GPL3')
depends=('python')
makedepends=('python-setuptools')
checkdepends=('python-nose')
source=("http://pypi.python.org/packages/source/h/html2text/html2text-$pkgver.tar.gz")


build() {
  cd "$srcdir/html2text-$pkgver"
  python setup.py build
}

check() {
  cd "$srcdir/html2text-$pkgver"
  PYTHONPATH=$PYTHONPATH:. python setup.py test --verbose
}

package() {
  cd "$srcdir/html2text-$pkgver"
  python setup.py install --root="$pkgdir" --optimize=1
  install -Dm644 README.md "$pkgdir/usr/share/doc/$pkgname/README.md"
  rm -f "$pkgdir/usr/bin/html2text"
}

# vim:set ts=2 sw=2 et:
md5sums=('59bccc9b56b472bc916b2b89ef49e245')
