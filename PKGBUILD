pkgname=softtweak-git
pkgver=1.0.ac279a9
pkgrel=1
pkgdesc="Kernel tweak for android system, Implemented KTweak by tytydraco "
arch=('any')
url="https://github.com/tytydraco/SoftTweak.git"
license=('GPL3')
depends=()
makedepends=('git')
source=("$pkgname"::'git+https://github.com/tytydraco/softtweak')
md5sums=('SKIP')
provides=(softtweak)

pkgver() {
  cd "$pkgname"
  echo "1.0.`git rev-parse --short HEAD`"
}

package() {
  cd "$srcdir/${pkgname}/"
  chmod +x softtweak
  mkdir -p "$pkgdir/usr/bin/"
  mkdir -p "$pkgdir/etc/systemd/system/"
  install -Dm744 ktweak "$pkgdir/usr/bin/softtweak"
  install -Dm644 ktweak.service "$pkgdir/etc/systemd/system/softtweak.service"
}