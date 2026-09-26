.. _tutorial_riskam:

Risk awareness with RiskAM
**************************

The Risk Awareness Module (RiskAM), in `risk-awareness-module <https://github.com/CoreSenseEU/risk-awareness-module>`_, computes in real time a risk score between 0 and 1 for visually navigated robots, considering the risk to humans around the robot. It combines proximity, gaze, position and approach sub-scores computed from an RGB-D camera.

Requirements
============

- An RGB camera and an absolute depth image in metres. The defaults are calibrated for Intel RealSense D4xx cameras.
- Optionally, the robot velocity (``cmd_vel``) and person tracking, to enable the path-aware and approach sub-scores.
- ROS 2. It is tested on Rolling.

Build
=====

.. code-block:: bash

   cd ~/ros2_ws/src
   git clone https://github.com/CoreSenseEU/risk-awareness-module.git
   cd ..
   colcon build --packages-select riskam riskam_ros riskam_msgs riskam_bringup
   source install/setup.bash

Run
===

.. code-block:: bash

   ros2 run riskam_ros riskam_node.py --ros-args -p camera_topic:=/your/color/topic

or, to launch the node together with the data logger:

.. code-block:: bash

   ros2 launch riskam_bringup riskam.launch.py run_logger:=true

The parameters are in ``riskam_bringup/config/riskam_config.yml``. The main ones are:

.. list-table::
   :header-rows: 1

   * - Parameter
     - Default
     - Purpose
   * - ``camera_topic``
     - ``/camera/camera/color/image_raw``
     - RGB input
   * - ``depth_topic``
     - ``/camera/camera/depth/image_rect_raw``
     - Depth input
   * - ``cmd_vel_topic``
     - ``/cmd_vel``
     - Robot velocity (optional)
   * - ``d_safe``
     - ``1.5`` m
     - Safety distance

Output
======

- ``/riskam/risk_score`` (``riskam_msgs/FloatStamped``): risk of the scene, between 0 and 1.
- ``/riskam/annotated_image`` (``sensor_msgs/Image``): visualisation overlay.
- ``/riskam/diagnostics`` (``diagnostic_msgs/DiagnosticArray``): timing and status of each sub-score.

The full reference of parameters and topics is in the `repository documentation <https://github.com/CoreSenseEU/risk-awareness-module/tree/main/docs>`_.
