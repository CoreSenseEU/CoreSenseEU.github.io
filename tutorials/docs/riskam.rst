.. _tutorial_riskam:

Risk awareness with RiskAM
**************************

The Risk Awareness Module (RiskAM), in `risk-awareness-module <https://github.com/CoreSenseEU/risk-awareness-module>`_, computes in real time a risk score between 0 and 1 for visually navigated robots, considering the risk to humans around the robot. It combines proximity, gaze, position and approach sub-scores computed from an RGB-D camera.

Requirements
============

- An RGB camera and an absolute depth image in metres. The defaults are calibrated for Intel RealSense D4xx cameras.
- Optionally, the robot velocity (``cmd_vel``) and person tracking, to enable the path-aware and approach sub-scores.
- ROS 2 Jazzy or Kilted.

Install with Pixi
=================

The four packages (``riskam``, ``riskam_msgs``, ``riskam_ros`` and ``riskam_bringup``) are in the CoreSense Pixi channels, so no ROS installation is needed:

.. code-block:: bash

   pixi init riskam_app -c https://prefix.dev/coresense-jazzy \
     -c https://prefix.dev/robostack-jazzy -c conda-forge
   cd riskam_app
   pixi add ros-jazzy-riskam-bringup ros-jazzy-ros2run ros-jazzy-ros2topic
   pixi shell

For Kilted, replace ``jazzy`` with ``kilted``. The packages pull in PyTorch and Ultralytics from conda-forge. In an installed copy, set ``RISKAM_ML_MODELS_DIR`` to a directory for the YOLO11n-Pose weights (``yolo11n-pose.pt``), which Ultralytics downloads there on first use if missing.

Build from source
=================

.. code-block:: bash

   cd ~/ros2_ws/src
   git clone https://github.com/CoreSenseEU/risk-awareness-module.git
   cd ..
   rosdep install --from-paths src --ignore-src -y
   colcon build --packages-select riskam riskam_ros riskam_msgs riskam_bringup
   source install/setup.bash

The repository also includes the Pixi manifests: ``pixi install`` and ``pixi run start`` in the repository root build and launch the module.

Run
===

.. code-block:: bash

   ros2 run riskam_ros riskam_node.py --ros-args -p camera_topic:=/your/color/topic

or, to launch the node together with the rosbag2 logger (``riskam_bagger``):

.. code-block:: bash

   ros2 launch riskam_bringup riskam.launch.py run_bagger:=true

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
