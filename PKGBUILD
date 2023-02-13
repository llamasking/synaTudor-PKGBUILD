pkgname=synatudor-git
_pkgdirname=synaTudor
pkgver=1.0.0
pkgrel=1
pkgdesc=""
arch=(x86_64)
url="https://github.com/Popax21/synaTudor/"
license=('unknown')
depends=(libfprint-tod)
makedepends=(innoextract ninja 'meson>=0.57.0')
provides=(synatudor)
conflicts=()
options=(!emptydirs)
source=("git+https://github.com/Popax21/synaTudor.git"
        "0001-update-install-dir.patch")
sha256sums=('SKIP'
            '956bb5e624866da379a49b5b1706bddf89a57a79d4c08f37699831219071bb84')

prepare() {
    cd "$_pkgdirname"
    patch --forward --strip=1 --input="${srcdir}/0001-update-install-dir.patch"
}

build() {
    INSTALL_DIR="/usr/bin" arch-meson $_pkgdirname build
    ninja -C build
}

package() {
    meson install -C build --destdir "$pkgdir"
}
