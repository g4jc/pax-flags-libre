# Contributors:
#   henning mueller <henning@orgizm.net>
#   Ahmad24, duncant, echoblack, niki, ShadowKyogre, s1gma, test0
#
# Find this package in the AUR:
#   https://aur.archlinux.org/packages/linux-pax-flags
#
# Please report bugs and new flags on GitHub:
#   https://github.com/nning/linux-pax-flags
#
# Forked libre version which blacklists non-free software for Parabola here:
# https://github.com/g4jc/pax-flags-libre
#

pkgname=pax-flags-libre
pkgdesc='Deactivates PaX flags for several binaries to work with PaX enabled kernels.'
pkgver=2.0.17
pkgrel=1
arch=(any)
url='https://github.com/g4jc/pax-flags-libre'
license=(GPL3)
depends=(ruby paxctl)
optdepends=('sudo: Run as root automatically.')
source=(
  $pkgname.sh $pkgname.rb $pkgname.8
  replicant.conf browsers.conf clamav.conf games.conf imagemagick.conf java.conf
  kde.conf polkit.conf qemu.conf ruby.conf simple.conf valgrind.conf wine.conf
)

package() {
  install -D -m755 $srcdir/$pkgname.sh $pkgdir/usr/bin/$pkgname
  install -D -m755 $srcdir/$pkgname.rb $pkgdir/usr/bin/$pkgname.rb
  install -D -m644 $srcdir/$pkgname.8  $pkgdir/usr/share/man/man8/$pkgname.8

  for config in $srcdir/*.conf; do
    install -D -m600 $config $pkgdir/usr/share/$pkgname/$(basename $config)
  done

  mkdir -p $pkgdir/etc/pax-flags-libre
}

sha256sums=('06295e9d2afea0ea01c42620f0cd5e3ae785bc42c2749d4bef52f7d5b8a043ce'
            '79367f1b72eb836557e24df20fc4ad142af55669c0fee1e3e7a0d34d35bfc9dc'
            '9d62896dd51be4979cd85bfcd09de219f6068ec312f27e2a66f7a2f2c78d1f38'
	    '7bbbad18a19150893916995723cd7e256a7b4e2baa5c2ff57bc27886c40f51fc'
            'aedce25acf41fffa7a5c15c2ad7e5034eb56bfedcde65612ae4bc3f86ef4841a'
            'bb87f4dce8e20f2ce601bdcb888dd688d8f0e9d0ab367e09c8081daffa15b03a'
            '95471682765c3c5ca31b29e3de7f8a07de6b2857e999dcdd714d062fe3da04ea'
	    '7dc92a303004c9d74a1fe4d40d75105a703366ade8b2b459b0aae8d6f8b62ed0'
            '71afe786955d149fe216ff1a60348562914a6820d3b7f9dc42aa44913062b04e'
            '01ddeec77c605e1d3aa00a1fdc4c3537989468ab78da5f37b893cdbcfe34176c'
            '1f205fddfb427a696fb00221a3007453e25fbbf180ea026c264d23eeac9e1870'
            '2736d0ef20d0127c34e132db38d8993dee3062ba0ac0cdf8d444a8d3665698b8'
            'e5562d68df885c5ceeb51709fc57c86d7b2c7849b9d99f828a77228878e25d71'
            '7d9f510e649e4ead08be3bb5f6fe1b6371b47a9fbb2f9b829cf329caa16bad94'
            'ea003c4201745cd0c4bcf5cec5ca2d0a79cc6b1b04ceaa276ace0ad0287b8c50'
	    'd78fe0a02b5801c70e3d64045b12c3cbee358689da9082d71003b1cffda73ee3')
