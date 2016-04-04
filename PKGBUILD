pkgname=waifu
pkgver=1.0
pkgrel=1
pkgdesc="Stream anime from torrents. Skip the downloads. Launch, click, watch."
arch=('x86_64')
url="http://www.waifu.ca/"
license=('GPL3')
makedepends=('zip')
options=('!strip')
install="waifu.install"
source=("http://waifu.ca/static/media/Waifu_linux64.tar.gz"
        "icon.png"
        "waifu.install"
        "waifu.desktop")
md5sums=('e79d42eeb496aadf4d3d2934c88e8e36'
         'cf39cfa760be1a1e25ed1609f564af4b'
         '6dbcc2ed6caef33d97c5dc5ffc43583c'
         'adaaaff59d725be879c5ae6bdef13242')


package() {
  cd "${srcdir}"

  install -dm755 "${pkgdir}/usr/share/${pkgname}" "${pkgdir}/usr/bin"
  install -Dm755 ${pkgname}_linux64/Waifu "${pkgdir}/usr/share/${pkgname}/"
  install -Dm644 ${pkgname}_linux64/{nw.pak,libffmpegsumo.so} "${pkgdir}/usr/share/${pkgname}/"
  ln -s "/usr/share/${pkgname}/Waifu" "${pkgdir}/usr/bin/waifu"
  install -Dm644 waifu.desktop "${pkgdir}/usr/share/applications/waifu.desktop"
  install -Dm644 icon.png "${pkgdir}/usr/share/pixmaps/waifu.png"
}
