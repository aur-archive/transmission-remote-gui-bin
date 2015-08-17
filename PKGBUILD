# Maintainer: Paul N. Maxwell <msg.maxwel@gmail.com>
pkgname=transmission-remote-gui-bin
pkgver=5.0.1
pkgrel=2
pkgdesc="Cross platform remote GUI for the Transmission daemon"
arch=('i686' 'x86_64')
url="http://code.google.com/p/transmisson-remote-gui/"
license=('GPL2')
depends=('gtk2')
makedepends=()
conflicts=('transmission-remote-gui-svn' 'transmission-remote-gui')
options=()
install=transmission-remote-gui.install

_carch=$CARCH
[ $_carch = "i686" ] && _carch="i386"

source=("http://transmisson-remote-gui.googlecode.com/files/transgui-${pkgver}-${_carch}-linux.zip"
        'transgui.desktop'
        'transgui.launcher')
noextract=()

md5sums=('f1198409c0065fa8867c0a70fff4b1e4'
         '9127df31bd6b2aa0df63a6603c984593'
         '972df0c768020926d2ce355fb0649e79')

if [ $_carch = "i386" ]; then
md5sums=('79e266f49e01c402b77f080d5e57672e'
         '9127df31bd6b2aa0df63a6603c984593'
         '972df0c768020926d2ce355fb0649e79')
fi

build() {
  echo "Building not needed.. Skipping.."
}

package() {
  cd "$srcdir"
  install -D -m 755 transgui $pkgdir/opt/TransGUI/transgui
  install -d -m 755 $pkgdir/opt/TransGUI/lang/
  install -D -m 644 lang/transgui.{be,cs,da,de,el,es,fi,fr,hr,hu,it,ko,lt,lv,nl,no,pl,pt_br,ro,ru,sv,tr,uk,zh,zh_tw} $pkgdir/opt/TransGUI/lang/
  install -D -m 644 history.txt $pkgdir/opt/TransGUI/history.txt
  install -D -m 644 readme.txt $pkgdir/opt/TransGUI/readme.txt
  install -D -m 644 LICENSE.txt $pkgdir/opt/TransGUI/LICENSE.txt
  install -D -m 644 transgui.png $pkgdir/opt/TransGUI/transgui.png
  install -d -m 755 $pkgdir/usr/share/pixmaps/
  ln -s /opt/TransGUI/transgui.png $pkgdir/usr/share/pixmaps/transgui.png
  install -D -m 644 transgui.desktop $pkgdir/usr/share/applications/transmission-remote-gui.desktop
  install -D -m 755 transgui.launcher $pkgdir/usr/bin/transgui
}

