#!/hint/bash -e
# Maintainer: jason ryan <jasonwryan@gmail.com>
# Contributor: megadriver <megadriver at gmx dot com>
# Contributor: Vasil Yonkov <bustervill at gmail dot com>
# Contributor: Guten Ye <ywzhaifei [at] gmail [dot] com>

pkgname=ruby-build-git
pkgver=20220324.r0.ga5ca3e4
pkgrel=1
pkgdesc="Compile and install Ruby"
arch=('any')
url="https://github.com/rbenv/${pkgname%-git}"
license=("MIT")
depends=('bash')
makedepends=('git')
provides=('ruby-build')
conflicts=('ruby-build')
source=("git+$url.git")
sha1sums=('SKIP')

pkgver() {
  cd "${pkgname%-git}"
  git describe --long | sed 's/^v//;s/-/.r/;s/-/./'
}

package() {
  cd "${pkgname%-git}"

  mkdir -p "$pkgdir/usr/bin"
  mkdir -p "$pkgdir/usr/share/ruby-build"

  cp bin/* "$pkgdir/usr/bin"
  cp share/ruby-build/* "$pkgdir/usr/share/ruby-build"
  install -D -m644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

# vim:set ts=2 sw=2 et:
