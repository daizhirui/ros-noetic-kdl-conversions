# Script generated with import_catkin_packages.py.
# For more information: https://github.com/bchretien/arch-ros-stacks.
pkgdesc="ROS - Conversion functions between KDL and geometry_msgs types."
url='https://wiki.ros.org/kdl_conversions'

pkgname='ros-noetic-kdl-conversions'
pkgver='1.13.2'
_pkgver_patch=0
arch=('any')
pkgrel=2
license=('BSD')

ros_makedepends=(
	ros-noetic-catkin
	ros-noetic-geometry-msgs
)

makedepends=(
	'cmake'
	'ros-build-tools'
	${ros_makedepends[@]}
	orocos-kdl
)

ros_depends=(
	ros-noetic-geometry-msgs
)

depends=(
	${ros_depends[@]}
	orocos-kdl
)

_commit="fe344b6c848b8239750ad7f8c7eccf86241396d3"
_dir="geometry-${_commit}/kdl_conversions"
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/ros/geometry/archive/${_commit}.tar.gz")
sha256sums=('d9ec545b272d37fcceadf6dd6c359570427d8f341760fac5fcd87424b78d2eae')

build() {
	# Use ROS environment variables.
	source /usr/share/ros-build-tools/clear-ros-env.sh
	[ -f /opt/ros/noetic/setup.bash ] && source /opt/ros/noetic/setup.bash

	# Create the build directory.
	[ -d ${srcdir}/build ] || mkdir ${srcdir}/build
	cd ${srcdir}/build

	# Build the project.
	cmake ${srcdir}/${_dir} \
		-DCATKIN_BUILD_BINARY_PACKAGE=ON \
		-DCMAKE_INSTALL_PREFIX=/opt/ros/noetic \
		-DPYTHON_EXECUTABLE=/usr/bin/python \
		-DSETUPTOOLS_DEB_LAYOUT=OFF
	make
}

package() {
	cd "${srcdir}/build"
	make DESTDIR="${pkgdir}/" install
}
