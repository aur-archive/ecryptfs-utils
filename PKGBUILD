# Contributor: Richard Murri <admin@richardmurri.com>
# Contributor: Michal Krenek <mikos@sg1.cz>

pkgname=ecryptfs-utils
pkgver=95
pkgrel=1
arch=(i686 x86_64)
pkgdesc="Enterprise-class stacked cryptographic filesystem for Linux"
url="https://launchpad.net/ecryptfs"
license=('GPL')
makedepends=('swig' 'intltool' 'gettext')
depends=('keyutils' 'openssl' 'nss' 'python2')
install=ecryptfs-utils.install
source=(http://launchpad.net/ecryptfs/trunk/${pkgver}/+download/${pkgname}_${pkgver}.orig.tar.gz)
options=(!libtool)
md5sums=('b015c89d9c684bd1c10b57c7c8d40577')

build() {
  cd "$srcdir/${pkgname}-${pkgver}"

  export PYTHON=python2
  export PATH=$PATH:/usr/lib/perl5/core_perl/bin
  ./configure --prefix=/usr
  make || return 1
  make DESTDIR=$pkgdir install
}
