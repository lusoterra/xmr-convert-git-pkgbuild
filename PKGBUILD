# Maintainer: Lev <lev@lusosterone.net>
pkgname=xmr-convert-git
pkgver=r2.9fa4e51
pkgrel=1
pkgdesc="Convert Cryptonote addresses to standard Monero (XMR) addresses"
arch=('x86_64' 'aarch64')
url="https://git.lusosterone.net/lev/xmr-convert"
license=('MIT')
depends=('glibc')
makedepends=('git')
provides=('xmr-convert')
conflicts=('xmr-convert')
source=("${pkgname}::git+${url}.git")
sha256sums=('SKIP')

pkgver() {
  cd "${pkgname}"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd "${pkgname}"
  make
}

package() {
  cd "${pkgname}"
  make DESTDIR="${pkgdir}" PREFIX=/usr install
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
