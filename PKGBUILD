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
pkgver=2.0.14
pkgrel=2
arch=(any)
url='https://github.com/g4jc/pax-flags-libre'
license=(GPL3)
depends=(ruby paxctl)
optdepends=('sudo: Run as root automatically.')
source=(
  $pkgname.sh $pkgname.rb $pkgname.8
  replicant.conf clamav.conf games.conf java.conf kde.conf polkit.conf qemu.conf
  ruby.conf simple.conf valgrind.conf
)

package() {
  install -D -m755 $srcdir/$pkgname.sh $pkgdir/usr/bin/$pkgname
  install -D -m755 $srcdir/$pkgname.rb $pkgdir/usr/bin/$pkgname.rb
  install -D -m644 $srcdir/$pkgname.8  $pkgdir/usr/share/man/man8/$pkgname.8

  for config in $srcdir/*.conf; do
    install -D -m600 $config $pkgdir/usr/share/$pkgname/$(basename $config)
  done

  mkdir -p $pkgdir/etc/pax-flags
}

sha256sums=('8581506830903ffcbb0876e4380d660ff044d9805d68f1432753c5bb99dc0db9'
            'ee66dc1087f501a7ebb89b0ec36125b94dc87ce560aa38c6d606dad1818d5b95'
            '65bc0cd02ed826c9fd79d3dda55235fed5aa794477d5610364faa0943390b161'
            '7bbbad18a19150893916995723cd7e256a7b4e2baa5c2ff57bc27886c40f51fc'
            'bb87f4dce8e20f2ce601bdcb888dd688d8f0e9d0ab367e09c8081daffa15b03a'
            '298bf32f4e8193d4cc5a4eb98369dc564afe51849046fd5673150cea51950985'
            '71afe786955d149fe216ff1a60348562914a6820d3b7f9dc42aa44913062b04e'
            '01ddeec77c605e1d3aa00a1fdc4c3537989468ab78da5f37b893cdbcfe34176c'
            '1f205fddfb427a696fb00221a3007453e25fbbf180ea026c264d23eeac9e1870'
            '2736d0ef20d0127c34e132db38d8993dee3062ba0ac0cdf8d444a8d3665698b8'
            '6171eefd363f2c70bed9ac41fae3458d9e03460fdaf079c99445482e9649555a'
            '5cd70e01fc7c8867d3ee9160fecf44c028947b54788a41833789c71ef5cef9a4'
            'ea003c4201745cd0c4bcf5cec5ca2d0a79cc6b1b04ceaa276ace0ad0287b8c50')
