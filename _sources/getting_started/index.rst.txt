.. _getting_started:

Getting Started
###############

The fastest way to try a released CoreSense package is `Pixi <https://pixi.sh>`_. Pixi installs ROS 2 and all the dependencies in a project folder, from the `RoboStack <https://robostack.github.io>`_ channels and the CoreSense channels. It does not need a system-wide ROS installation, ``rosdep`` or ``colcon``, and it works on any Linux distribution.

This example installs EasyNav, the CoreSense navigation framework, for ROS 2 Jazzy.

.. note::

  See :ref:`build-instructions` to install with ``apt`` on Ubuntu, or to build from source.

1. Install Pixi (version 0.77 or newer) and open a new terminal:

   .. code-block:: bash

      curl -fsSL https://pixi.sh/install.sh | bash

2. Create a project that uses the CoreSense and RoboStack channels for Jazzy:

   .. code-block:: bash

      pixi init my_app -c https://prefix.dev/coresense-jazzy \
        -c https://prefix.dev/robostack-jazzy -c conda-forge
      cd my_app

3. Add the packages. ``ros-jazzy-ros2run`` provides the ``ros2`` command line tool:

   .. code-block:: bash

      pixi add ros-jazzy-easynav ros-jazzy-easynav-simple-planner ros-jazzy-ros2run

4. Run any ROS 2 command inside the environment. Nothing needs to be sourced:

   .. code-block:: bash

      pixi run ros2 pkg list | grep easynav
      pixi shell    # or open a shell with the environment activated

For ROS 2 Kilted, replace ``jazzy`` with ``kilted`` in the channels and in the package names.

To learn how to use EasyNav, see its documentation at https://easynavigation.github.io.

Available channels
******************

=============  =================================================
Distribution   Channel
=============  =================================================
Jazzy (LTS)    https://prefix.dev/channels/coresense-jazzy
Kilted         https://prefix.dev/channels/coresense-kilted
=============  =================================================

The channel pages list all the available packages and versions.
