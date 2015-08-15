# Maintainer: Paolo Stivanin <http://www.polslinux.it>

pkgname=firefox-beta-bin-it
_pkgreal=firefox-beta-bin
_pkgnome=firefox-beta
pkgver=14.0b9
pkgrel=1
_lang=it
_srcurl=ftp://ftp.mozilla.org/pub/firefox/releases
pkgdesc='Standalone web browser from mozilla.org! Latest beta with Italian language'
url='http://www.mozilla.org/projects/firefox'
arch=('i686' 'x86_64')
depends=('dbus-glib' 'desktop-file-utils' 'libxt' 'mime-types' 'nss' 'shared-mime-info')
license=('MPL' 'GPL' 'LGPL')
provides=("firefox=$pkgver")
source=(ftp://ftp.mozilla.org/pub/mozilla.org/firefox/releases/${pkgver}/linux-${CARCH}/it/firefox-${pkgver}.tar.bz2
        firefox-beta.desktop
	firefox-beta-safe.desktop)
md5sums=("$(curl -s ${_srcurl}/${pkgver}/MD5SUMS | grep linux-${CARCH}/it | grep firefox-${pkgver}.tar.bz2 | sed '2d' | cut -f1 -d' ')"
	 'ae3521941bdf0d760dd1b4c36f203d14'
	 '275ff1cc88e3080578a7262411cd223e')
	  
package() {
	cd ${srcdir}

	mkdir -p ${pkgdir}/{usr/{bin,share/{applications,pixmaps}},opt}
	cp -r firefox ${pkgdir}/opt/${_pkgreal}-$pkgver

	ln -s /opt/${_pkgreal}-${pkgver}/firefox ${pkgdir}/usr/bin/${_pkgreal}
	install -m644 ${srcdir}/{$_pkgnome.desktop,$_pkgnome-safe.desktop} ${pkgdir}/usr/share/applications/
	install -m644 ${srcdir}/firefox/icons/mozicon128.png ${pkgdir}/usr/share/pixmaps/${_pkgreal}-icon.png
}
