pkgname=habitat
pkgver=0.23.0
pkgrel=1
pkgdesc="Application automation framework that allows you to build applications that have automation built-in"
arch=('x86_64')
url="https://www.habitat.sh/"
license=('Apache')
depends=('libarchive' 'libsodium')
makedepends=('cargo')
source=("${pkgname}::git+https://github.com/habitat-sh/habitat.git#tag=${pkgver}")
sha256sums=('SKIP')

build() {
  export CARGO_HOME="${srcdir}/cargo-repository"
  cd "${srcdir}/${pkgname}"
  make
}

package() {
  install -D -m755 "${srcdir}/${pkgname}/target/debug/hab" "${pkgdir}/usr/bin/hab"
}
