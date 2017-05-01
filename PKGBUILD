# Maintainer: killhellokitty <killhellokitty at gmail dot com>
_gitname=nufraw-thumbnailer
pkgname=${_gitname}-git
pkgver=2017.05.01.039
pkgrel=1
pkgdesc="Generates thumbnails for RAW images using nufraw, a new version of the popular raw digital images manipulator ufraw."
arch=('any')
url="https://github.com/killhellokitty/nufraw-thumbnailer"
license=('GPL2')
depends=('gimp-nufraw')
makedepends=('nufraw' 'git')
provides=(ufraw.thumbnailer)
conflicts=(ufraw.thumbnailer)
source=('nufraw-thumbnailer::git+https://github.com/killhellokitty/$_gitname.git')
sha256sums=('db296f2f7f35bca3a174efb0eb392b3b17bd94b341851429a3dff411b1c2fc73'
            '9d72c398bf54d7d6c692485fac078e32faf620bd15c1fc92c0ff9185176e0b7e'
            '1272311cf734f107b399fcfb239d50f687ff7de6347a5b726558fbc76871883a')

pkgver() {
  cd "$srcdir/${pkgname}"
  git rev-list --count HEAD
}

package() {
	make DESTDIR="$pkgdir/" install
  install -D -m644 "${pkgname}/LICENSE" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
