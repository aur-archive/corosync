# Maintainer: gls <ghostlovescorebg at gmail dot com>
# Fixed by Thermi <noel at familie-kuntze dot de>
pkgname=corosync
pkgver=2.3.4
pkgrel=2
pkgdesc="Cluster engine for nodal communication systems with additional features for implementing high availability within applications."
arch=('i686' 'x86_64')
url="http://www.corosync.org/"
license=('BSD')
makedepends=('nss' 'libstatgrab' 'net-snmp' 'libqb')
depends=('nss' 'libstatgrab' 'net-snmp' 'libqb')
provides=('corosync=2.1.0')
conflicts=('corosync1')
source=("http://corosync.org/download/corosync-$pkgver.tar.gz"
	"corosync.service")
md5sums=('4b0f36a1dc014527e5b192265dbd7e70'
         '9ce64dfbc32cdcf7ad2c33385aab1401')

build() {

	cd ${srcdir}/${pkgname}-${pkgver}
	./configure --sbindir=/usr/bin \
              --sysconfdir=/etc \
	      --libdir=/usr/lib \
              --localstatedir=/var \
              --enable-systemd \
              --enable-monitoring \
              --enable-snmp \
              --enable-dbus \
              --with-systemddir=/usr/lib/systemd/system
  	make

}

package() {

	cd ${srcdir}/${pkgname}-${pkgver}
  	make DESTDIR="${pkgdir}" install

}
