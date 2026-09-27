.. _tutorial_cs4home:

Cognitive modules with cs4home_architecture
*******************************************

This tutorial builds and runs the example cognitive modules of `cs4home_examples <https://github.com/CoreSenseEU/cs4home_examples>`_, which use the ROS 2 implementation of the CoreSense architecture, `cs4home_architecture <https://github.com/CoreSenseEU/cs4home_architecture>`_. See :ref:`design` for the structure of a cognitive module.

The repository contains two examples:

- **Face module**: face identities from ``hri_face_detect`` are converted into knowledge-graph updates.
- **YOLO module**: camera images are processed by YOLO and published as detections.

Build
=====

Requires ROS 2 and ``vcstool``.

.. code-block:: bash

   mkdir -p ~/cs4home_examples_ws/src
   cd ~/cs4home_examples_ws/src
   git clone https://github.com/CoreSenseEU/cs4home_examples.git
   vcs import --recursive < cs4home_examples/thirdparty.repos
   cd ..
   python3 -m venv --system-site-packages py_deps
   source py_deps/bin/activate
   pip install -r src/thirdparty/hri_face_detect/requirements.txt
   pip install -r src/thirdparty/yolov8_ros/requirements.txt
   rosdep install --from-paths src --ignore-src -r -y
   colcon build --symlink-install
   source install/setup.bash

Run the YOLO module
===================

Start a camera driver, then:

.. code-block:: bash

   ros2 launch cs4home_simple_project yolo_example.launch.py

Run the face module
===================

Start ``hri_face_detect``, then run the module with its parameters:

.. code-block:: bash

   ros2 run cs4home_simple_project face_module --ros-args \
     --params-file src/cs4home_examples/cs4home_simple_project/config/params_simple.yaml

The result can be inspected with the knowledge-graph RQt plugin.

Create your own module
======================

`cs_functional_module_template <https://github.com/CoreSenseEU/cs_functional_module_template>`_ is a starting point for a new module. More complete examples are the perception modules of the social testbed: `cs4home_sound_module <https://github.com/CoreSenseEU/cs4home_sound_module>`_ and `cs4home_vision_module <https://github.com/CoreSenseEU/cs4home_vision_module>`_.
