# Maintainer: Mauro Ziliani <mauro@faresoftware.it>


pkgname="upd72020x-load"
pkgver="20210814"
pkgrel="1"

arch=(x86_64)

depends=(upd72020x-fw)
install=${pkgname}.install
source=(git+https://github.com/markusj/upd72020x-load
	set-upd72020-fw-file.patch)
md5sums=(SKIP
	571ac24964c51be4ddb6c55f49405a3e)


prepare() {
	cd "${srcdir}"
	echo "Patching..."
	patch --forward --strip=0 --input="${srcdir}/set-upd72020-fw-file.patch"
}

build() {
	cd "${srcdir}/${pkgname}"
	make
}

package() {
	cd "${srcdir}/${pkgname}"
	install -d -m 0755 ${pkgdir}/usr/bin
	install -m 0755 ${srcdir}/${pkgname}/upd72020x-load 		${pkgdir}/usr/bin
	install -m 0755 ${srcdir}/${pkgname}/upd72020x-check-and-init   ${pkgdir}/usr/bin
}
