# Script generated with Bloom
pkgdesc="ROS - This package contains a specialization of the gazebo_ros_control plugin. The cob_gazebo_ros_control plugin allows Multi-HardwareInterface-Support."
url='http://ros.org/wiki/cob_gazebo_ros_control'

pkgname='ros-kinetic-cob-gazebo-ros-control'
pkgver='0.7.2_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-controller-manager'
'ros-kinetic-gazebo-ros'
'ros-kinetic-gazebo-ros-control'
'ros-kinetic-hardware-interface'
'ros-kinetic-joint-limits-interface'
'ros-kinetic-pluginlib'
'ros-kinetic-roscpp'
'ros-kinetic-transmission-interface'
'ros-kinetic-urdf'
)

depends=('ros-kinetic-controller-manager'
'ros-kinetic-gazebo-ros'
'ros-kinetic-gazebo-ros-control'
'ros-kinetic-hardware-interface'
'ros-kinetic-joint-limits-interface'
'ros-kinetic-pluginlib'
'ros-kinetic-roscpp'
'ros-kinetic-transmission-interface'
'ros-kinetic-urdf'
)

conflicts=()
replaces=()

_dir=cob_gazebo_ros_control
source=()
md5sums=()

prepare() {
    cp -R $startdir/cob_gazebo_ros_control $srcdir/cob_gazebo_ros_control
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

