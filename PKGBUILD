# Script generated with Bloom
pkgdesc="ROS - C++ client library to access semantic maps within the world canvas framework."
url='http://ros.org/wiki/world_canvas_client_cpp'

pkgname='ros-kinetic-world-canvas-client-cpp'
pkgver='0.2.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-roscpp'
'ros-kinetic-unique-id'
'ros-kinetic-uuid-msgs'
'ros-kinetic-visualization-msgs'
'ros-kinetic-world-canvas-msgs'
)

depends=('ros-kinetic-roscpp'
'ros-kinetic-unique-id'
'ros-kinetic-uuid-msgs'
'ros-kinetic-visualization-msgs'
'ros-kinetic-world-canvas-msgs'
)

conflicts=()
replaces=()

_dir=world_canvas_client_cpp
source=()
md5sums=()

prepare() {
    cp -R $startdir/world_canvas_client_cpp $srcdir/world_canvas_client_cpp
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

