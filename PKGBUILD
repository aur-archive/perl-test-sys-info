# Maintainer: Jason St. John <jstjohn .. purdue . edu>
# Contributor: Sebastian Köhler <sebkoehler@whoami.org.uk>

_perlmod=Test-Sys-Info
_modnamespace=Test
pkgname=perl-test-sys-info
pkgver=0.20
pkgrel=7
pkgdesc="Test::Sys::Info - Centralized test suite for Sys::Info"
arch=('i686' 'x86_64')
url="http://search.cpan.org/dist/${_perlmod}"
license=('GPL' 'PerlArtistic')
options=('!emptydirs')
source=("http://cpan.org/modules/by-module/${_modnamespace}/${_perlmod}-${pkgver}.tar.gz")
sha512sums=('d403073fd426ff420cbc8bd8e9846a1b653d2ccb04aa45229a99717a53f0e02279b74d8d0e4c63c70ee2471e24d084d6d9bcecaa5a5be64b1d4e1f7c9a77230a')

build() {
	cd "${_perlmod}-${pkgver}"

	# Install module in vendor directories.
	PERL_MM_USE_DEFAULT=1 perl Makefile.PL INSTALLDIRS=vendor
	make
}

check() {
	cd "${_perlmod}-${pkgver}"
	make test
}

package() {
	cd "${_perlmod}-${pkgver}"
	make install DESTDIR="${pkgdir}"
}
