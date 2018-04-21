# Script generated with Bloom
pkgdesc="ROS - Topic tools for treating messages as variant types."
url='http://github.com/ethz-asl/ros-topic-variant'

pkgname='ros-kinetic-variant-topic-tools'
pkgver='0.1.3_1'
pkgrel=1
arch=('any')
license=('GNU Lesser General Public License (LGPL)'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-roscpp'
'ros-kinetic-roslib'
'ros-kinetic-variant-msgs'
)

depends=('ros-kinetic-roscpp'
'ros-kinetic-roslib'
'ros-kinetic-variant-msgs'
)

conflicts=()
replaces=()

_dir=variant_topic_tools
source=()
md5sums=()

prepare() {
    cp -R $startdir/variant_topic_tools $srcdir/variant_topic_tools
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

