#!/bin/bash

# Based on the original PKGBUILD by Felix Barz <skycoder42.de@gmx.de>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/qdep/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/qdep/discussions>

pkgname=qdep
pkgver=1.1.1
pkgrel=2
pkgdesc="A very basic yet simple to use dependency management tool for qmake based projects."
arch=(
  "any"
)
url="https://github.com/Skycoder42/qdep"
license=(
  "BSD"
)
install="$pkgname.install"
depends=(
  "qt5-base"
  "python"
  "python-argcomplete"
  "python-lockfile"
  "python-appdirs"
)
optdepends=(
  "qt5-tools: Needed for lupdate to generate qdep translations"
)
makedepends=(
  "python-setuptools"
)
source=(
  "${pkgname}-${pkgver}.tar.gz"::"https://github.com/Skycoder42/${pkgname}/archive/refs/tags/${pkgver}.tar.gz"
)
sha512sums=(
  "5c45128f51e96d751dcd6ef8c0f5056fdd40ccfe58a438800ef1d5c3b01dc1404d57fd8d28a283c9b6a685c45cc3b1ac5456c823029cb68c4a017934394dcf28"
)

package() {

  cd "${srcdir}/${pkgname}-${pkgver}"

  python setup.py install --root="${pkgdir}/" --optimize=1

  install -D -m644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
