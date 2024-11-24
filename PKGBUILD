# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Pellegrino Prevete <pellegrinoprevete@gmail.com>
# Maintainer: Truocolo <truocolo@aol.com>
# Contributor: Filipe Bertelli <filipebertelli@tutanota.com>

_node="nodejs"
_proj="hardhat"
_pkgbase="${_proj}-ignition-ethers"
pkgname="${_pkgbase}"
_pkgdesc=(
  "declarative system for deploying"
  "smart contracts on Ethereum Virtual"
  "Machine networks"
)
_pkgdesc="${_pkgdesc[*]}"
pkgver=0.15.8
pkgrel=1
arch=(
  'arm'
  'x86_64'
  'mips'
  'i686'
  'pentium4'
  'aarch64'
  'armv7l'
  'armv6l'
)
_ns="NomicFoundation"
_pub="nomicfoundation"
url="https://github.com/${_ns}/${_pkgbase}"
license=(
  'custom'
)
depends=(
  "${_proj}>=2.22.3"
  "${_node}-ethers"
)
makedepends=(
  'npm'
)
provides=(
  "${_node}-${_pkgbase}=${pkgver}"
)
conflicts=(
  "${_node}-${_pkgbase}"
)
_npm="http://registry.npmjs.org"
source=(
  "${_npm}/@${_pub}/${_pkgbase}/-/${_pkgbase}-${pkgver}.tgz"
)
noextract=(
  "${_pkgbase}-${pkgver}.tgz"
)
sha512sums=(
  'e44bfc71704a82aa8eb055f159ef228a3b1169b58677f55c971dd20bdd3729e29578f76cb15b197184ed44d45c23045c3c9d1120a24f219cfb30d0e8eb8977fb'
)

package() {
  local \
    _npm_options=()
  _npm_options=(
    -g
    # --user=root
    --prefix="${pkgdir}/usr"
    )
  npm \
    install \
      "${_npm_options[@]}" \
      "${srcdir}/${_pkgbase}-${pkgver}.tgz"
  rm \
    -fr \
      "${pkgdir}/usr/etc"
  # Fix npm derp
  find \
    "${pkgdir}/usr" \
    -type d \
    -exec \
      chmod \
        755 \
	'{}' \
	+
}

# vim:set sw=2 sts=-1 et:
