.. _tutorial_pixi_release:

Publish a package in the CoreSense Pixi channels
************************************************

This tutorial publishes a ROS 2 package in the CoreSense Pixi channels, so that anyone can install it with Pixi on any Linux distribution. It summarises the second exercise of the ROSCon 2026 workshop `Declarative ROS workspaces with Pixi <https://prefix-dev.github.io/roscon-2026-declarative-ros-workspaces-with-pixi/>`_, and it is also part of the `CoreSense/ROS Development Guidelines (D5.1) <https://www.coresense.eu/doc/CS-019.pdf>`_.

The examples use a package called ``my_package`` and ROS 2 Jazzy. For Kilted, replace ``jazzy`` with ``kilted`` everywhere.

1. Install Pixi
===============

.. code-block:: bash

   curl -fsSL https://pixi.sh/install.sh | bash

2. Add a package manifest
=========================

Put a ``pixi.toml`` next to the ``package.xml`` of each package, and another one at the root of the repository for the workspace:

.. code-block:: text

   my_repository/
     pixi.toml               <- workspace manifest
     my_package/
       package.xml
       CMakeLists.txt
       pixi.toml             <- package manifest

The package manifest says which build backend to use and that the package may be published. Everything else, including name, version and dependencies, comes from ``package.xml``:

.. code-block:: toml

   [package]
   publish = true

   [package.build.backend]
   name = "pixi-build-ros"
   workspace = true

For ``ros2 run`` to find an executable, install it in ``lib/<package_name>``, as in any ROS 2 package.

3. Add the workspace manifest
=============================

.. code-block:: toml

   [workspace]
   name = "my_repository"
   channels = ["https://prefix.dev/coresense-jazzy",
               "https://prefix.dev/robostack-jazzy",
               "conda-forge"]
   platforms = ["linux-64"]
   preview = ["pixi-build"]

   [workspace.dependencies]
   pixi-build-ros = ">=0.7.5"

   [dependencies]
   ros-jazzy-my-package = { path = "my_package" }
   ros-jazzy-ros2run = "*"

   [tasks]
   start = "ros2 run my_package my_node"

The conda name of ``my_package`` is ``ros-jazzy-my-package``: distribution prefix, and hyphens instead of underscores.

4. Build and test locally
=========================

.. code-block:: bash

   pixi install        # builds my_package and installs it in the environment
   pixi run start      # runs the node, no sourcing needed

If the build fails, the usual reason is a dependency in ``package.xml`` with a different name in RoboStack. It can be mapped with the ``extra-package-mappings`` option of `pixi-build-ros <https://pixi.sh/latest/build/backends/pixi-build-ros/>`_.

5. Publish to a local folder first
==================================

.. code-block:: bash

   pixi publish --target-channel ./output
   find output -name "*.conda"

6. Publish to the CoreSense channel
===================================

You need a prefix.dev account with write permission on the CoreSense channels. Ask the WP5 leader to add your account, create an API key in your prefix.dev account settings, and then run:

.. code-block:: bash

   pixi auth login prefix.dev --token <YOUR_API_KEY>
   pixi publish --dry-run --target-channel https://prefix.dev/coresense-jazzy
   pixi publish --target-channel https://prefix.dev/coresense-jazzy

A version that already exists in the channel is skipped, so increase the version in ``package.xml`` for every release. Packages are built for the platform of the machine where Pixi runs.

7. Install the published package
================================

.. code-block:: bash

   pixi init my_app -c https://prefix.dev/coresense-jazzy \
     -c https://prefix.dev/robostack-jazzy -c conda-forge
   cd my_app
   pixi add ros-jazzy-my-package ros-jazzy-ros2run
   pixi run ros2 run my_package my_node
