# Maintainer:  Gabriel Souza Franco <Z2FicmllbGZyYW5jb3NvdXphQGdtYWlsLmNvbQ==>
# Contributor: mickele
# Contributor: Brice Méalier <mealier_brice *at* yahoo *dot* fr>
# Contributor: Essien Ita Essien <me *at* essienitaessien *dot* com>
# Contributor: Tobias Sandmann <tSa *at* gmx *dot* eu>
# Contributor: pfm <nl081130 *at* yahoo *dot* de>
# Contributor: mortbauer <mortbauer *at* gmail *dot* com>

pkgname=omniorbpy
pkgver=4.2.4
pkgrel=1
pkgdesc="omniORB is a CORBA object request broker for C++ and Python."
arch=(i686 x86_64)
url="http://omniorb.sourceforge.net/"
license=('LGPL')
depends=('omniorb' 'python')
conflicts=('omniorbpy-omg' 'pyorbit')
provides=('pyorbit')
source=(http://downloads.sourceforge.net/omniorb/omniORBpy-$pkgver.tar.bz2 patch)
sha256sums=('dae8d867559cc934002b756bc01ad7fabbc63f19c2d52f755369989a7a1d27b6'
    '677108480a016c79f49c497ff372a2e20d7f17acfe12594515c6c629d486027d')

prepare() {
  cd "$srcdir/omniORBpy-$pkgver"
  patch -p0 -i "$srcdir/patch"
}


build() {
  cd "$srcdir/omniORBpy-$pkgver"
  ./configure --prefix=/usr
  make
}

package() {
  cd "$srcdir/omniORBpy-$pkgver"
  make DESTDIR="$pkgdir" install

  # adjust directory permissions
  find "$pkgdir" -type d -exec chmod 755 '{}' +
}
