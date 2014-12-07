pkgname=waifu
pkgver=latest
pkgrel=2
pkgdesc="Stream anime from torrents. Skip the downloads. Launch, click, watch."
arch=('x86_64')
url="http://www.waifu.ca/"
license=('GPL3')
makedepends=('zip')
depends=()
options=('!strip')
install="waifu.install"
md5sums=('cae952ed5c5d071ac77fe99066b98229'
         'cf39cfa760be1a1e25ed1609f564af4b'
         '6dbcc2ed6caef33d97c5dc5ffc43583c'
         'adaaaff59d725be879c5ae6bdef13242')

source=("http://www.waifu.ca/waifu-linux64.tar.gz"
        "icon.png"
        "waifu.install"
        "waifu.desktop")

package() {
  cd "${srcdir}"

  install -dm755 "${pkgdir}/opt/${pkgname}/"
  install -dm755 "${pkgdir}/usr/share/${pkgname}"
  install -dm755 "${pkgdir}/usr/bin"

  # Program
  echo "${pkgdir}/usr/share/${pkgname}/"
  install -Dm755 ${srcdir}/linux64/Waifu "${pkgdir}/usr/share/${pkgname}/"
  install -Dm644 ${srcdir}/linux64/nw.pak "${pkgdir}/usr/share/${pkgname}/"
  install -Dm644 ${srcdir}/linux64/libffmpegsumo.so "${pkgdir}/usr/share/${pkgname}/"

  # Link to program
  mkdir -p "${pkgdir}/usr/bin"
  ln -s "/usr/share/${pkgname}/Waifu" "${pkgdir}/usr/bin/waifu"

  # Desktop file
  install -Dm644 "${srcdir}/waifu.desktop" "${pkgdir}/usr/share/applications/waifu.desktop"

  # Icon
  install -Dm644 "${srcdir}/icon.png" "${pkgdir}/usr/share/pixmaps/waifu.png"
}
