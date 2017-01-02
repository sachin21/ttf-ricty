# Maintainer: Tatsunori Aoki <ginjiro.135 at gmail dot com>
# Contributor: eagletmt <eagletmt@gmail.com>
pkgname=ttf-ricty
pkgver=4.0.2b
pkgrel=1
pkgdesc='Japanese TrueType font for developers by mixing Inconsolata and Migu 1M.'
arch=('any')
url='http://www.rs.tus.ac.jp/yyusa/ricty.html'
license=('custom')
depends=('fontconfig' 'xorg-font-utils')
makedepends=('fontforge' 'ttf-inconsolata>=20090215-4' 'ttf-migu')
install=ttf.install
source=('http://www.rs.tus.ac.jp/yyusa/ricty/ricty_generator.sh'
        'http://www.rs.tus.ac.jp/yyusa/ricty/regular2oblique_converter.pe')
sha1sums=('c38475f680d1c0d648949a1e70722b5c31895690'
          '21ee4dcc0a64264351d8ef3f289dbb43aa76f198')

build() {
  cd "$srcdir"
  chmod +x ./ricty_generator.sh
  ./ricty_generator.sh /usr/share/fonts/TTF/{Inconsolata-Regular.ttf,Inconsolata-Bold.ttf,migu-1m-regular.ttf,migu-1m-bold.ttf}
}

package() {
  cd "$srcdir"
  install -d "$pkgdir/usr/share/fonts/TTF"
  install -m644 *.ttf "$pkgdir/usr/share/fonts/TTF/"
  install -d "$pkgdir/usr/share/licenses/$pkgname"
}
