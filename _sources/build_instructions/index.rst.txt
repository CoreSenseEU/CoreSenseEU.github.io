.. _build-instructions:

Build and Install
#################

Install
*******

CoreSenseEU install


Build
*****

Install ROS
-----------

Please install ROS 2 via the usual `build instructions <https://index.ros.org/doc/ros2/Installation>`_ for your desired distribution.

Build CoreSenseEU
-----------------

Create a new workspace, ``CoreSenseEU_ws``, and clone CoreSenseEU master branch into it and build it. 

.. code:: bash

  mkdir -p ~/CoreSenseEU_ws/src
  cd ~/CoreSenseEU_ws/src
  git clone https://github.com/CoreSenseEU/whatever.git
  
  cd ~/CoreSenseEU_ws
  rosdep install -y -r -q --from-paths src --ignore-src --rosdistro <ros2-distro>
  colcon build --symlink-install

