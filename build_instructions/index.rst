.. _build-instructions:

Build and Install
#################

Install
*******

CoreSense install


Build
*****

Install ROS
-----------

Please install ROS 2 via the usual `build instructions <https://index.ros.org/doc/ros2/Installation>`_ for your desired distribution.

Build CoreSense
---------------

Create a new workspace, ``CoreSense_ws``, and clone CoreSense master branch into it and build it. 

.. code:: bash

  mkdir -p ~/CoreSense_ws/src
  cd ~/CoreSense_ws/src
  git clone https://github.com/CoreSenseEU/whatever.git
  
  cd ~/CoreSense_ws
  rosdep install -y -r -q --from-paths src --ignore-src --rosdistro <ros2-distro>
  colcon build --symlink-install

