# Maintainer:  Gabriel Souza Franco <Z2FicmllbGZyYW5jb3NvdXphQGdtYWlsLmNvbQ==>
# Contributor: mickele
# Contributor: Brice Méalier <mealier_brice *at* yahoo *dot* fr>
# Contributor: Essien Ita Essien <me *at* essienitaessien *dot* com>
# Contributor: Tobias Sandmann <tSa *at* gmx *dot* eu>
# Contributor: pfm <nl081130 *at* yahoo *dot* de>
# Contributor: mortbauer <mortbauer *at* gmail *dot* com>

pkgname=omniorbpy
pkgver=4.3.0
pkgrel=1
pkgdesc="A CORBA object request broker for C++ and Python."
arch=(i686 x86_64)
url="http://omniorb.sourceforge.net/"
license=('LGPL')
depends=('omniorb' 'python')
source=(http://downloads.sourceforge.net/omniorb/omniORBpy-$pkgver.tar.bz2)
sha256sums=('fffcfdfc34fd6e2fcc45d803d7d5db5bd4d188a747ff9f82b3684a753e001b4d')

build() {
  cd "$srcdir/omniORBpy-$pkgver"
  ./configure --prefix=/usr
  make
}

package() {
  cd "$srcdir/omniORBpy-$pkgver"

  # already available in omniORB
  sed -i 's/omniidl_be//' python3/dir.mk

  make DESTDIR="$pkgdir" install

  # adjust directory permissions
  find "$pkgdir" -type d -exec chmod 755 '{}' +
}
