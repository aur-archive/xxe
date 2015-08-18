# Maintainer: Sabart Otto - Seberm <seberm[at]gmail[dot]com>

pkgname=xxe
pkgver=5.8.0
_versionEdited=${pkgver//./_}
pkgrel=1
pkgdesc="XMLmind XML Editor allows to edit large, complex, modular, XML  documents. This package contains Personal Edition"
arch=('i686' 'x86_64')
url="http://www.xmlmind.com/xmleditor"
license=('custom')
depends=('java-runtime=7')
makedepends=('imagemagick')
install=xxe.install
source=("http://www.xmlmind.net/xmleditor/_download/xxe-eval-${_versionEdited}.tar.gz" xxe.sh xxe.desktop)

build() {
	cd $srcdir
	mkdir $pkgdir/opt
	mv xxe-eval-${_versionEdited} $pkgdir/opt/xxe

	# We need to remove win files
	rm $pkgdir/opt/xxe/bin/*.bat
	rm $pkgdir/opt/xxe/bin/*.exe

	# Install the license file
	install -D -m645 $pkgdir/opt/xxe/legal/xxe-eval.LICENSE $pkgdir/usr/share/licenses/$pkgname/LICENSE

	# logo and menu file
	mkdir -p $pkgdir/usr/share/{applications,pixmaps}
	mv $pkgdir/opt/xxe/bin/icon/xxe.png $pkgdir/usr/share/pixmaps/xxe.png
	install    -m644 $srcdir/xxe.desktop $pkgdir/usr/share/applications/
	install -D -m755 $srcdir/xxe.sh $pkgdir/etc/profile.d/xxe.sh
}

md5sums=('a019ebe1d826832d92fe8ca458930ec1'
         'ccd373358e00dfcf8055067bc614ec39'
         '5665a6b917f6a79e94e09995e7ae63d1')
