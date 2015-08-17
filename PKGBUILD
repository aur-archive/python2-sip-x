# $Id$
# Maintainer: <xia0er@gmail.com>
# Contributor: Andrea Scarpino <andrea@archlinux.org>
# Contributor: Douglas Soares de Andrade <douglas@archlinux.org>
# Contributor: riai <riai@bigfoot.com>, Ben <ben@benmazer.net>

pkgname=('python2-sip-x')
pkgbase=sip
pkgver=4.14.2
pkgrel=1
pkgdesc="python2-sip that doesn't depend on sip package or python3"
#pkgdesc="A tool that makes it easy to create Python2 bindings for C and C++ libraries"
arch=('i686' 'x86_64')
url="http://www.riverbankcomputing.com/software/sip/"
license=('custom:"sip"')
depends=('python2')
replaces=('python2-sip' 'sip')
provides=('python2-sip' 'sip')

makedepends=('python2')
source=("http://downloads.sourceforge.net/pyqt/${pkgbase}-${pkgver}.tar.gz")
md5sums=('b93442e745b3be2fad89de0686a76ce9')

#export LDFLAGS="${LDFLAGS//-Wl,--as-needed}"
#export LDFLAGS=""

build() {
  cd "${srcdir}"
  #mv ${_pkgname}-${pkgver} python2-${_pkgname}-${pkgver}

  #cd "${srcdir}/${pkgbase}-${pkgver}"
  #python2 configure.py CFLAGS="${CFLAGS}" LFLAGS="${LDFLAGS}"
  #make
  
  ### Python2 version ###
  cd "${srcdir}/${pkgbase}-${pkgver}"
  python2 configure.py CFLAGS="${CFLAGS}" LFLAGS="${LDFLAGS}"
  make

  cd "${srcdir}/${pkgbase}-${pkgver}"
  make DESTDIR="${pkgdir}" install

  install -Dm644 sipconfig.py "${pkgdir}"/usr/lib/python2.7/site-packages/sipconfig.py
  install -Dm644 sipdistutils.py "${pkgdir}"/usr/lib/python2.7/site-packages/sipdistutils.py

  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
