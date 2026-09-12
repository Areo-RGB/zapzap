# Maintainer: Areo-RGB
# PKGBUILD for ZapZap (CachyOS / Arch Linux)
pkgname=zapzap
pkgver=7.4.4
pkgrel=1
pkgdesc="WhatsApp Desktop client for Linux with built-in Stealth Read Mode"
arch=('x86_64' 'aarch64')
url="https://github.com/Areo-RGB/zapzap"
license=('GPL-3.0-or-later')
depends=('python' 'python-pyqt6' 'python-pyqt6-webengine' 'qt6-webengine' 'python-dbus')
makedepends=('git' 'python-build' 'python-installer' 'python-wheel' 'python-setuptools')
provides=('zapzap')
conflicts=('zapzap-git')

build() {
  cd "$startdir"
  python -m build --wheel --no-isolation
}

package() {
  cd "$startdir"
  python -m installer --destdir="$pkgdir" dist/*.whl
  if [ -f "zapzap/assets/icons/com.rtosta.zapzap.svg" ]; then
    install -Dm644 "zapzap/assets/icons/com.rtosta.zapzap.svg" "$pkgdir/usr/share/icons/hicolor/scalable/apps/com.rtosta.zapzap.svg"
  fi
  if [ -f "zapzap/assets/com.rtosta.zapzap.desktop" ]; then
    install -Dm644 "zapzap/assets/com.rtosta.zapzap.desktop" "$pkgdir/usr/share/applications/com.rtosta.zapzap.desktop"
  fi
}
