# Maintainer: Ch4s3r <lamprecht.patrick1@gmail.com>
pkgname=argocd-autopilot-bin
pkgver=v0.2.28
pkgrel=1
pkgdesc="Argocd autopilot binary downloaded from Github"
arch=(x86_64)
url="https://github.com/argoproj-labs/argocd-autopilot"
license=('Apache')
provides=(argocd-autopilot)

pkgver() {
  curl -s "https://api.github.com/repos/argoproj-labs/argocd-autopilot/releases/latest" | grep '"tag_name"' | sed -E 's/.*"([^"]+)".*/\1/'
}

package() {
	curl -L --output - https://github.com/argoproj-labs/argocd-autopilot/releases/download/$pkgver/argocd-autopilot-linux-amd64.tar.gz | tar zx
	install -Dm755 argocd-autopilot-* "$pkgdir/usr/bin/argocd-autopilot"
}
