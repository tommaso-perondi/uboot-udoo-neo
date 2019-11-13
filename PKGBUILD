pkgname=uboot-udoo-neo
pkgver=2016.09.y
pkgrel=1
pkgdesc="U-Boot for UDOO NEO"
arch=('armv7h')
url="https://github.com/tommaso-perondi/u-boot.git"
makedepends=('bc' 'dtc' 'git')
license=('GPL')
install=${pkgname}.install
source=("https://github.com/tommaso-perondi/u-boot/archive/u-boot-2016.09.y.zip")
md5sums=('2a715f52ddb38b153d06279a643c759f')

prepare() {
  unzip u-boot-${pkgver}.zip
}

build() {
  cd u-boot-${pkgver}
  
  unset CFLAGS CXXFLAGS LDFLAGS
  
  make distclean
  make udoo_neo_defconfig
  make EXTRAVERSION=-${pkgrel}
}

package_uboot-udoo() {
  cd u-boot-${pkgver}

  mkdir -p "${pkgdir}"/boot
  cp SPL u-boot.img "${pkgdir}"/boot
}
