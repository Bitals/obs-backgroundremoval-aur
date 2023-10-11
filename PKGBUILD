# Maintainer: Bitals <me at bitals dot xyz>
# Co-maintainer: Ng Oon-Ee <n g o o n e e dot t a l k @ gmail dot com>
# Co-maintainer: PedroHLC <root@pedrohlc.com>
pkgname=obs-backgroundremoval

pkgver=1.1.7
pkgrel=1
pkgdesc='Background removal plugin for OBS studio'
_source="${pkgname}-${pkgver}"

arch=(x86_64)
url='https://github.com/royshil/obs-backgroundremoval'
license=('GPL2')
depends=('obs-studio' 'opencv' 'curl')
makedepends=('cmake' 'ninja')
source=("${_source}.tar.gz::$url/archive/refs/tags/${pkgver}.tar.gz")
sha512sums=('30852287afc2258ecda19459ad0b9414b8b9129e5d1419dda956496328586dd66d526de11dc7e34021fd795d27ec9bb27eacf1ace594f15420107a8795cb1a4d')

build() {
  cd "$_source"
  cmake -B build --preset linux-x86_64 -DLINUX_PORTABLE=OFF -DUSE_SYSTEM_OPENCV=ON -DUSE_SYSTEM_CURL=ON
  cmake --build build
}

package() {
  cd "$_source"
  cmake --install build --prefix "$pkgdir/usr"
}
