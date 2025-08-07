pkgname=macropad_tool-git
_pkgname=macropad_tool
pkgver=0.1.r144.56911748
pkgrel=1
pkgdesc="tool to program a macropad"
arch=('x86_64')
url="https://github.com/kamaaina/${_pkgname}"
license=('AGPL3')
depends=()
makedepends=('git' 'rust')
source=("git+https://github.com/kamaaina/$_pkgname.git")
sha256sums=('SKIP')

build() {
  cd "$_pkgname"
  cargo build --release --workspace
}

package() {
  install -Dm755 "${_pkgname}/target/release/${_pkgname//_/-}" "$pkgdir/usr/bin/${_pkgname//_/-}"
  install -Dm 644 "${_pkgname}/80-macropad.rules" "${pkgdir}/etc/udev/rules.d/80-macropad.rules"

}
