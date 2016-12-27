# Maintainer: Flat <Flat@imo.uto.moe>
pkgname=parallel-rust
pkgver=0.7.0
pkgrel=1
pkgdesc="Inspired by GNU Parallel, a command-line CPU load balancer written in Rust."
arch=('i686' 'x86_64')
url="https://github.com/mmstick/parallel"
license=('MIT')
depends=('gcc-libs-multilib')
makedepends=('rust-nightly' 'cargo-nightly')
optdepends=('dash: increased performance over sh')
provides=('parallel')
conflicts=('parallel')
source=("https://github.com/mmstick/parallel/archive/$pkgver.tar.gz")
md5sums=('f4ba609e871ead210fcee524a110d9fb')

build() {
	cd "parallel-$pkgver"
	cargo build --release
}

package() {
	cd "parallel-$pkgver"
	mkdir -p $pkgdir/usr/bin
	mkdir -p $pkgdir/usr/share/licenses/$pkgname
	install target/release/parallel $pkgdir/usr/bin
	install LICENSE $pkgdir/usr/share/licenses/$pkgname
}
