# Contributor: imrahil (Hugo Lobo) <hugo_alobo@hotmail.com>
pkgname=kdeplasma-addons-applets-stackfolder
pkgver=0.2.1
pkgrel=1

original_pkgname=kdeplasma-applets-stackfolder
original_pkgrel=1

pkgdesc="Browse the stack of folders"
arch=('i686' 'x86_64')
url="http://www.mandriva.com"
license="GPL"
makedepends=('cmake' 'automoc4')
replaces=('plasma-applet-stackfolder')
source=(http://ftp.free.fr/mirrors/ftp.mandriva.com/MandrivaLinux/devel/2012/SRPMS/main/release/$original_pkgname-$pkgver-$original_pkgrel.src.rpm)
md5sums=('244cbee29cc6a58eb9b7b013a0c9d9cf')
build() {
	cd $srcdir
        tar -jxvf $original_pkgname-$pkgver.tar.bz2
	cd  $original_pkgname-$pkgver
	rm -rf build
	mkdir build
	cd build
	cmake -DCMAKE_INSTALL_PREFIX=`kde4-config --prefix` ../
	make clean
	make VERBOSE=1 || return 1
	make DESTDIR=$pkgdir install || return 1
}
