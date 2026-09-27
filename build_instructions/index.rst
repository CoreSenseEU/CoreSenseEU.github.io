.. _build-instructions:

Build and Install
#################

CoreSense software can be installed in three ways. Use binary packages when they exist, and build from source for the rest.

==========================  ==============================  ======================================
Method                      Requires                        Available for
==========================  ==============================  ======================================
Pixi (conda packages)       Pixi, any Linux distribution    Packages in the CoreSense channels
``apt`` (Debian packages)   Ubuntu with ROS 2 installed     Packages in the ROS 2 buildfarm
From source                 ROS 2 and ``colcon``            All the repositories
==========================  ==============================  ======================================

The :ref:`packages` page shows which method is available for each package.

Install with Pixi
*****************

See :ref:`getting_started`. The CoreSense channels are:

- Jazzy: https://prefix.dev/channels/coresense-jazzy
- Kilted: https://prefix.dev/channels/coresense-kilted

Install with apt
****************

Install ROS 2 following the `official instructions <https://docs.ros.org/en/jazzy/Installation.html>`_, then install the released packages. For example, for EasyNav on Jazzy:

.. code-block:: bash

   sudo apt install ros-jazzy-easynav ros-jazzy-easynav-simple-planner

Build from source
*****************

Install ROS 2 following the `official instructions <https://docs.ros.org/en/jazzy/Installation.html>`_. Then create a workspace, clone the repository, install its dependencies and build it. For example, for the CoreSense architecture used in the social testbed:

.. code-block:: bash

   mkdir -p ~/coresense_ws/src
   cd ~/coresense_ws/src
   git clone https://github.com/CoreSenseEU/cs4home_architecture.git
   cd ~/coresense_ws
   rosdep install --from-paths src --ignore-src -r -y
   colcon build --symlink-install
   source install/setup.bash

Replace the repository with the one you need. Each repository README describes its specific dependencies and branches.
