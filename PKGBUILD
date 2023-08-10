pkgname=sublime-text
pkgver=4.4152
pkgrel=1
pkgdesc="Sophisticated text editor for code, html and prose - dev build"
arch=('x86_64')
url="http://www.sublimetext.com"
license=('custom')
depends=('libpng' 'gtk2')
install=${pkgname}.install
conflicts=('sublime-text-dev')
replaces=('sublime-text-dev')

source=(
  "https://download.sublimetext.com/sublime_text_build_${pkgver:2}_x64.tar.xz"
)
md5sums=('37667127bfba8355de03d27e58bec1b6')

package() {
  cd "${srcdir}"

  install -dm755 "${pkgdir}/opt"
  cp --preserve=mode -r "sublime_text" "${pkgdir}/opt/sublime_text"

  for res in 128x128 16x16 256x256 32x32 48x48; do
    install -dm755 "${pkgdir}/usr/share/icons/hicolor/${res}/apps"
    ln -s "/opt/sublime_text/Icon/${res}/sublime-text.png" "${pkgdir}/usr/share/icons/hicolor/${res}/apps/sublime-text.png"
  done

  install -dm755 "${pkgdir}/usr/share/applications"
  install -Dm644 "sublime_text/sublime_text.desktop" "${pkgdir}/usr/share/applications/sublime_text.desktop"

  install -dm755 "${pkgdir}/usr/bin"
  ln -s "/opt/sublime_text/sublime_text" "${pkgdir}/usr/bin/subl"
}
