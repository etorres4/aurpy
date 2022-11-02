# Maintainer: Eric Torres <erictorres4@protonmail.com>
pkgname=pkgpy
pkgver=0.1
pkgrel=1
pkgdesc="An AUR tool written in Python"
arch=('any')
url="https://github.com/etorres4/aurpy"
license=('MIT')
groups=()
depends=(python python-requests python-termcolor)
makedepends=(git python-setuptools)
checkdepends=(python=pytest)
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
backup=()
source=("${pkgname}::git+file:///home/etorres/Projects/aurpy")
sha256sums=('SKIP')

build() {
	cd "$srcdir/${pkgname}"
    python setup.py build
}

check() {
	cd "$srcdir/${pkgname}"
    pytest
}

package() {
	cd "$srcdir/${pkgname}"
    python setup.py install --root="$pkgdir" --optimize=1

    # Install zsh completions
    #for completion in zsh/*; do
        #install -Dm644 "${completion}" "${pkgdir}/usr/share/zsh/site-functions/$(basename "$completion")"
    #done
}
