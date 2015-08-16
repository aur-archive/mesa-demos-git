# Maintainer: Limao Luo <luolimao+AUR@gmail.com>
# Contributor: Lone_Wolf <lonewolf@xs4all.nl>
# Contributor: Perry3D <perry3d@gmail.com>

pkgname=mesa-demos-git
pkgver=8.1.0.19.g93c9871
pkgrel=1
pkgdesc="The mesa demos (glxinfo, glxgears, etc.), built from the git master branch."
arch=(i686 x86_64)
url=http://mesa3d.org/
license=(custom)
depends=(glew freeglut mesa)
makedepends=(git)
provides=(${pkgname%-*}=$pkgver)
conflicts=(${pkgname%-*})
source=($pkgname::git://anongit.freedesktop.org/mesa/demos
    LICENSE)
sha256sums=('SKIP'
    '7fdc119cf53c8ca65396ea73f6d10af641ba41ea1dd2bd44a824726e01c8b3f2')
sha512sums=('SKIP'
    '25da77914dded10c1f432ebcbf29941124138824ceecaf1367b3deedafaecabc082d463abcfa3d15abff59f177491472b505bcb5ba0c4a51bb6b93b4721a23c2')

pkgver() {
    cd $pkgname/
    git describe | sed 's/^mesa-demos-//;s/-/./g'
}

build() {
    cd $pkgname/
    ./autogen.sh --prefix=/usr
    make
}

package() {
    make -C $pkgname DESTDIR="$pkgdir" install
    install -Dm755 LICENSE "$pkgdir"/usr/share/licenses/$pkgname/LICENSE
}
