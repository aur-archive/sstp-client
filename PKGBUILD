# Maintainer: Kirill Malyshev <keryascorpio at gmail.com>

pkgname=sstp-client
pkgver=1.0.9
pkgrel=2
pkgdesc="SSTP VPN implementation that allows remote access to Microsoft Windows 2008 Server"
arch=("i686" "x86_64")
url="http://sstp-client.sourceforge.net/"
license=('GPL2')
conflicts=('sstp-client-svn-stable')
provides=()
depends=('ppp' 'openssl')
makedepends=('gcc' 'ppp')
optdepends=()
source=("http://garr.dl.sourceforge.net/project/${pkgname}/${pkgname}/${pkgver}/${pkgname}_${pkgver}.tar.gz")
md5sums=('45f452e1ee8bc83470c3c51024403cea')

build() {
  cd $srcdir
  tar -xzf "${pkgname}_${pkgver}.tar.gz"
  cd "${pkgname}"
  
  ./configure --prefix=/usr --localstatedir=/
  make
}

package() {
  cd "${srcdir}/${pkgname}"
  make DESTDIR="${pkgdir}" install
  
  install -d ${pkgdir}/run/sstpc/
  mv ${pkgdir}/usr/sbin ${pkgdir}/usr/bin
}

# End of file
