# Script generated with Bloom
pkgdesc="ROS - The dummy_slam_broadcaster package"


pkgname='ros-kinetic-dummy-slam-broadcaster'
pkgver='0.1.3_1'
pkgrel=1
arch=('any')
license=('TODO'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-geometry-msgs'
'ros-kinetic-nav-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-tf'
)

depends=('ros-kinetic-geometry-msgs'
'ros-kinetic-nav-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-tf'
)

conflicts=()
replaces=()

_dir=dummy_slam_broadcaster
source=()
md5sums=()

prepare() {
    cp -R $startdir/dummy_slam_broadcaster $srcdir/dummy_slam_broadcaster
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

