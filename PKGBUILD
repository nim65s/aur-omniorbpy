# Maintainer:  Gabriel Souza Franco <Z2FicmllbGZyYW5jb3NvdXphQGdtYWlsLmNvbQ==>
# Contributor: mickele
# Contributor: Brice Méalier <mealier_brice *at* yahoo *dot* fr>
# Contributor: Essien Ita Essien <me *at* essienitaessien *dot* com>
# Contributor: Tobias Sandmann <tSa *at* gmx *dot* eu>
# Contributor: pfm <nl081130 *at* yahoo *dot* de>
# Contributor: mortbauer <mortbauer *at* gmail *dot* com>

pkgname=omniorbpy
pkgver=4.2.3
pkgrel=1
pkgdesc="omniORB is a CORBA object request broker for C++ and Python."
arch=(i686 x86_64)
url="http://omniorb.sourceforge.net/"
license=('LGPL')
depends=('omniorb' 'python')
conflicts=('omniorbpy-omg' 'pyorbit')
provides=('pyorbit')
source=(http://downloads.sourceforge.net/omniorb/omniORBpy-$pkgver.tar.bz2
patch-a{a,b,d,e,f,g}
)
sha256sums=('5c601888e57c7664324357a1be50f2739c468057b46fba29821a25069fc0aee5'
'db5410276801c908eaa37cfffe74c1d7dbf97ccc1cf7368366cbd72341a89996'
'8f21b5b54e000aa8baf2a4ec3104526bed0715aed85916e8f7fe1eff91d69e93'
'5a5b86209126403362e2935feecffc7178bd6921d466b727ed61aeec0567ab76'
'658d2f59cd2a0e83b43d17c8c6bbf5ab1837de0b2d1ba0cc483acf7bb929862a'
'ca0b6572d9268baab87fa1e75c4705baac468fea4592bdacc446035a55e806b9'
'199fedb20a7d7e0814145954aa70f6a3527bfacd43fa64079a51de87a618e461'
)

prepare() {
  # Apply patches from robotpkg
  cd "$srcdir/omniORBpy-$pkgver"
  for p in a b d e f g
  do patch -p0 -i "$srcdir/patch-a$p"
  done
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
