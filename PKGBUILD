# Script generated with Bloom
pkgdesc="ROS - Examples showing how to use C++ and Python client libraries to access semantic maps within the world canvas framework."
url='http://ros.org/wiki/world_canvas_client_examples'

pkgname='ros-kinetic-world-canvas-client-examples'
pkgver='0.2.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-nav-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-unique-id'
'ros-kinetic-uuid-msgs'
'ros-kinetic-world-canvas-client-cpp'
'ros-kinetic-world-canvas-msgs'
'ros-kinetic-yocs-msgs'
)

depends=('ros-kinetic-nav-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-unique-id'
'ros-kinetic-uuid-msgs'
'ros-kinetic-world-canvas-client-cpp'
'ros-kinetic-world-canvas-client-py'
'ros-kinetic-world-canvas-msgs'
'ros-kinetic-yocs-msgs'
)

conflicts=()
replaces=()

_dir=world_canvas_client_examples
source=()
md5sums=()

prepare() {
    cp -R $startdir/world_canvas_client_examples $srcdir/world_canvas_client_examples
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

