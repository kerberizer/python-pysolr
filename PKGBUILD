# Maintainer: Luchesar V. ILIEV <luchesar.iliev@gmail.com>

pkgbase='python-pysolr'

pkgname=(
    'python-pysolr'
    'python2-pysolr'
)

pkgver=3.8.1
pkgrel=1

pkgdesc='Lightweight Python client for Apache Solr'
arch=('any')
url='https://github.com/django-haystack/pysolr'
license=('Apache')

makedepends=(
    'python'
    'python-requests'
    'python-setuptools'
    'python2'
    'python2-requests'
    'python2-setuptools'
)

_name='pysolr'
_pypi='files.pythonhosted.org/packages/source'

source=(
    "https://${_pypi}/${_name::1}/${_name}/${_name}-${pkgver}.tar.gz"
)

sha512sums=(
    '34489f32cdcbcb7e8109d6d94339fcb200b1367a188a0b9fedf587a77cd64412570b3a796a4da4e0abe6fa3e443a401c4dc0e4946bdc437dd810fee7eabd54a4'
)

build() {
    cd "${srcdir}/${_name}-${pkgver}"
    python setup.py build
}

package_python-pysolr() {
    depends=(
        'python'
        'python-requests'
    )
    optdepends=(
        'python-kazoo: for SolrCloud mode'
        'python-simplejson: use simplejson instead of the stdlib implementation'
    )
    cd "${srcdir}/${_name}-${pkgver}"
    python setup.py install --root="${pkgdir}/" --optimize=1 --skip-build
}

package_python2-pysolr() {
    depends=(
        'python2'
        'python2-requests'
    )
    optdepends=(
        'python2-kazoo: for SolrCloud mode'
        'python2-simplejson: use simplejson instead of the stdlib implementation'
    )
    cd "${srcdir}/${_name}-${pkgver}"
    python2 setup.py install --root="${pkgdir}/" --optimize=1 --skip-build
}

# vim:set ts=4 sts=4 sw=4 tw=100 et ft=sh:
