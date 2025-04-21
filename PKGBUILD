pkgname=topaz-videoai-beta
pkgver=5.0.3.1.b
pkgrel=1
pkgdesc="Video processing tool providing state-of-the-art AI filters for FFmpeg"
arch=('x86_64')
url="https://www.topazlabs.com"
license=('LicenseRef-TopazLabs-VideoAI')
depends=('vulkan-driver' 'glibc' 'libxcb' 'xcb-util-cursor' 'gstreamer' 'gst-plugins-base-libs' 'gst-plugins-bad-libs'
	'gst-plugins-base' 'gst-plugins-good' 'gst-plugins-bad' 'gst-plugins-ugly' 'gst-libav' 'gst-plugin-gtk'
	'gst-plugin-qmlgl' 'libunwind' 'gtk2' 'inter-font')
source=("$pkgname-$pkgver.deb::https://downloads.topazlabs.com/deploy/TopazVideoAIBeta/${pkgver}/TopazVideoAIBeta_${pkgver}_amd64.deb"
	"EULA.pdf::https://downloads.topazlabs.com/web-assets/Topaz%20-%20EULA%20%28FL%202.05.25%29.pdf")
sha256sums=('258627001c685aa9feed34a013b48003456f5fc5239151d6a5d5440b51fc795e'
	'448fd94b44dd0d96ea64313b5fa471c9e00d8b98889afcc8679c5d7a81fe1b5d')
noextract=("$pkgname-$pkgver.deb")

package() {
	bsdtar -O -xf "${pkgname}_${pkgver}.deb" 'data.tar*' | bsdtar -C "${pkgdir}" -xf - opt
	install -Dm644 EULA.pdf "${pkgdir}/usr/share/licenses/${pkgname}/EULA.pdf"
	install -Dm644 "${srcdir}"/README "${pkgdir}/usr/share/licenses/${pkgname}/README"
	install -Dm755 "${srcdir}/videoaiBETA-login" "${pkgdir}/usr/local/bin/videoaiBETA-login"
	install -Dm755 "${srcdir}/videoaiBETA-run" "${pkgdir}/usr/local/bin/videoaiBETA-run"
	install -Dt "${pkgdir}"/usr/share/applications "${srcdir}/TopazVideoAIBETA.desktop"
}
