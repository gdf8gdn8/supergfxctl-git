# Maintainer: Static_Rocket

pkgname=supergfxctl-git
pkgver=2.0.5.r0.gab8f1a8
pkgrel=1
pkgdesc="Asus laptop gfx ctl"
arch=('x86_64')
url="https://gitlab.com/asus-linux/supergfxctl"
license=('MPL2')
depends=('libusb' 'udev' 'systemd' 'asusctl-git')
optdepends=('acpi_call: fan control')
makedepends=('git') 
provides=('supergfxctl')
#conflicts=('')
source=('git+https://gitlab.com/asus-linux/supergfxctl')
md5sums=('SKIP')
_gitdir=${pkgname%"-git"}

pkgver() {
	cd "$srcdir/$_gitdir"
	git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
	cd "$srcdir/$_gitdir"
	make build
}

package() {
	cd "$srcdir/$_gitdir"
	make DESTDIR="$pkgdir" install

#	systemctl enable --now supergfxd.service

#	systemctl start supergfxd.service
}

