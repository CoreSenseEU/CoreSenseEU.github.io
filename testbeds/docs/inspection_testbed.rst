.. _inspection_testbeds:

TB2: Inspection Testbed
***********************

The objective of this testbed is to validate the CoreSense architecture with a Drone Swarm Autonomous Inspection. In this guide we present a configurable simulation environment that will be used for validate in simulation the architecture developed in this project.

In this testbed we leverage on the `Aerostack2 <https://github.com/aerostack2/aerostack2>`_ framework, a ROS 2 based framework for the development of autonomous aerial systems.

---------
Setup
---------

Aerostack2 Installation
=======================

Follow the instructions in `Aerostack2 Getting Started <https://aerostack2.github.io/_00_getting_started/index.html>`_.

An additional ROS2 package shall be installed for this project:

.. attention:: We encourage users to use the github ssh keys for cloning the repo. More information can be found at `github ssh docs <https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories#cloning-with-ssh-urls>`_

.. code-block:: bash

   mkdir ~/aerostack2_ws/src -p # avoid if aerostack2 has been installed from source
   cd ~/aerostack2_ws/src
   git clone git@github.com:CoreSenseEU/TB2_Panel_Inspection_Simulation.git
   cd .. 
   rosdep install -y -r -q --from-paths src --ignore-src
   colcon build --symlink-install



AS2 project requirements
========================

Additionally install the project execution dependencies, in `Aerostack2 project prerequisites <https://aerostack2.github.io/_02_examples/index.html#prerequisites>`_.

Inspection Testbed project
==========================


First clone the project repo with:

.. code-block:: bash

   git clone git@github.com:CoreSenseEU/TB2_Panel_Inspection_Simulation.git

To start using this project, please go to the root folder of the project.

----------------------
Simulation Environment
----------------------

.. figure:: ../images/GazeboView2.png
   :scale: 50
   :class: with-shadow

---------
Execution
---------

The execution will open a simulation in Gazebo and the Aerostack2 components will use simulation time.


In order to launch the simulation for the photovoltaic inspection launch:

.. code-block:: bash

    ./launch_as2.bash -n 4 -p 5 -r 4

The flags for the launcher are:

- ``-n``: especify the number of drones.
- ``-p``: the number of pannel per row
- ``-r``: the number of rows

.. _project_gazebo_simulated_single_drone:

This will open a simulation for **N** drones alongside the Aerostack2 components necessary for the mission execution (one per drone). We use `tmux <https://github.com/tmux/tmux/wiki>`_ for handling the execution of multiple sessions one per drone.

Each drone is equipped with:
  1. GPS
  2. RGB Camera
  3. Gimbal

See `Aerostack2 Common Interfaces Documentation <https://aerostack2.github.io/_08_ros2_common_interfaces/aerial_platform/index.html#topics>`_ for more information about them.
Below an example of an image retrieved from one drone can be found.

.. figure:: ../images/PanelImage.png
   :scale: 30
   :class: with-shadow


An example mission can be launch for making the drones go to a target panel by launching:

.. code-block:: bash

    python3 mission.py


To do a clean exit of tmux, execute:

.. code-block:: bash

    ./stop.bash
