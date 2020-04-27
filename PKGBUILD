# Maintainer: jason ryan <jasonwryan@gmail.com>
# Contributor : Martin Wimpress <code@flexion.org>

pkgname=syncthing-bin
_realname=syncthing
pkgver=1.4.2
pkgrel=1
pkgdesc="Open Source Continuous Replication / Cluster Synchronization Thing: binary."
url="http://syncthing.net/"
arch=('x86_64')
license=('MPLv2')
provides=("syncthing=$pkgver")
conflicts=('syncthing')
source=(
  "https://github.com/syncthing/${_realname}/releases/download/v${pkgver}/${_realname}-linux-amd64-v${pkgver}.tar.gz"
  'syncthing.1'
)
sha512sums=('c2652464829d42b6cc24253d26e23886d2b5b50e91ae264580219fa85690b9c925878eff609145e71227e1da1660f8e73e3b8b94a978487b6d2d2f58265054d3'
            'ba63aa6513b387fc28290d8ade603eea9b23c583c03e9353a226fc38ced8d43e4e00716bd59058407d686ee70fb7e5f4e849b844f15e74d3dd33937fd36af300')

package() {
    cd "${_realname}-linux-amd64-v${pkgver}"
    install -D -m 755 ${_realname} "${pkgdir}/usr/bin/${_realname}"
    install -D -m 644 LICENSE.txt "${pkgdir}/usr/share/licenses/${_realname}/LICENSE"
    install -D -m 644 README.txt "${pkgdir}/usr/share/doc/${_realname}/README.md"
    install -D -m 644 "etc/linux-systemd/system/${_realname}@.service" \
                      "${pkgdir}/usr/lib/systemd/system/${_realname}@.service"
    install -D -m 644 "etc/linux-systemd/user/${_realname}.service" \
                      "${pkgdir}/usr/lib/systemd/user/${_realname}.service"
    install -D -m 644 "../${_realname}.1" "${pkgdir}/usr/share/man/man1/${_realname}.1"
}

# vim:set ts=2 sw=2 et:
