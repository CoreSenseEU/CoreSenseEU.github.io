.. _packages:

Software catalogue
##################

All the CoreSense software is open source and hosted in the `CoreSense GitHub organisation <https://github.com/CoreSenseEU>`_. This page lists the main repositories, grouped by topic. The *Install* column shows how each one can be installed (see :ref:`build-instructions`): **Pixi**, **apt** or **source**.

At the end of the project, on 30 September 2026, 29 packages of 14 repositories were added to the CoreSense Pixi channels, for ROS 2 Jazzy and Kilted. When only some packages of a repository are in the channels, the *Install* column names them.

Architecture
************

.. list-table::
   :header-rows: 1
   :widths: 30 55 15

   * - Repository
     - Description
     - Install
   * - `cs4home_architecture <https://github.com/CoreSenseEU/cs4home_architecture>`_
     - ROS 2 implementation of the CoreSense architecture: cognitive modules (afferent, core, efferent, meta and coupling components) and flows.
     - Pixi (``cs4home_core``), source
   * - `cs4home_examples <https://github.com/CoreSenseEU/cs4home_examples>`_
     - Example cognitive modules built with ``cs4home_architecture``.
     - source
   * - `cs_functional_module_template <https://github.com/CoreSenseEU/cs_functional_module_template>`_
     - Template to start a new functional module.
     - source
   * - `coresense_understanding <https://github.com/CoreSenseEU/coresense_understanding>`_
     - Understanding system: generates strategies to obtain models with given properties.
     - source
   * - `understanding-logic <https://github.com/CoreSenseEU/understanding-logic>`_
     - Logic of the understanding core.
     - source
   * - `coresense_understanding_examples <https://github.com/CoreSenseEU/coresense_understanding_examples>`_
     - Example engines for the understanding system.
     - source
   * - `decision_system <https://github.com/CoreSenseEU/decision_system>`_
     - CoreSense decision system for ROS 2.
     - Pixi (all but ``krr_btcpp_ros2``), source
   * - `coresense_common <https://github.com/CoreSenseEU/coresense_common>`_
     - Common messages, bringup and behaviour-tree controller of the understanding system.
     - Pixi (``coresense_msgs``), source
   * - `coresense_engine_examples <https://github.com/CoreSenseEU/coresense_engine_examples>`_
     - Examples of CoreSense engine nodes.
     - Pixi (``coresense_example_msgs``), source
   * - `triplestar_kb <https://github.com/CoreSenseEU/triplestar_kb>`_
     - Knowledge base for ROS 2 based on RDF-star and RDF 1.2.
     - source
   * - `knowledge_core <https://github.com/CoreSenseEU/knowledge_core>`_
     - RDFlib-backed minimalistic knowledge base with ROS 2 API, OWL2 reasoning and event subscriptions. Used as the per-drone KB in the inspection testbed.
     - source
   * - `coresense_vampire <https://github.com/CoreSenseEU/coresense_vampire>`_
     - ROS 2 node that wraps the Vampire automated theorem prover.
     - Pixi, source
   * - `cso <https://github.com/CoreSenseEU/cso>`_
     - CoreSense Ontology, resolvable at https://w3id.org/coresense/cso.
     - --

Cognitive modules and structures
********************************

.. list-table::
   :header-rows: 1
   :widths: 30 55 15

   * - Repository
     - Description
     - Install
   * - `EasyNavigation <https://github.com/EasyNavigation/EasyNavigation>`_ and `easynav_plugins <https://github.com/EasyNavigation/easynav_plugins>`_
     - EasyNav, a plugin-based, real-time navigation framework able to include semantic and awareness representations. Documentation: https://easynavigation.github.io.
     - Pixi, apt
   * - `risk-awareness-module <https://github.com/CoreSenseEU/risk-awareness-module>`_
     - Risk awareness module (RiskAM): real-time risk score of visually navigated robots. See :ref:`tutorial_riskam`.
     - Pixi, source
   * - `physics-aware-module <https://github.com/CoreSenseEU/physics-aware-module>`_
     - Physics-aware modelling module based on neuro-evolutionary symbolic regression.
     - Pixi, source
   * - `fms <https://github.com/CoreSenseEU/fms>`_
     - Cognitive structure to deploy AI foundation models inside CoreSense systems.
     - source
   * - `cs-ne <https://github.com/CoreSenseEU/cs-ne>`_
     - CoreSense Navigation Essential.
     - source
   * - `cs4home_sound_module <https://github.com/CoreSenseEU/cs4home_sound_module>`_
     - Cognitive module for sound perception.
     - Pixi (``sound_msgs``), source
   * - `cs4home_vision_module <https://github.com/CoreSenseEU/cs4home_vision_module>`_
     - Cognitive module for visual perception.
     - Pixi (``cs4home_msgs``), source
   * - `cs4home_person_tracker_module <https://github.com/CoreSenseEU/cs4home_person_tracker_module>`_
     - Person tracking from camera and laser detections.
     - source
   * - `cs4home-explainability <https://github.com/CoreSenseEU/cs4home-explainability>`_
     - Explainability framework based on behaviour-tree status and component evidence.
     - Pixi (``explainability_msgs`` and two explainers), source
   * - `coresense-explainability <https://github.com/CoreSenseEU/coresense-explainability>`_
     - Explainability framework templates: example component explainers and explainer selector, to start custom explainers.
     - Pixi (the three example explainers), source

Toolchain
*********

.. list-table::
   :header-rows: 1
   :widths: 30 55 15

   * - Repository
     - Description
     - Install
   * - `rossdl <https://github.com/CoreSenseEU/rossdl>`_
     - ROS System Definition Language: model-based description of ROS 2 systems and code generation.
     - Pixi (``rossdl_cmake``), source
   * - `RosTooling <https://github.com/ipa320/RosTooling>`_
     - Eclipse-based IDE to model ROS systems. See :ref:`toolchain_introduction`.
     - update site
   * - `CS_ros2model_TBs <https://github.com/CoreSenseEU/CS_ros2model_TBs>`_
     - Models of the testbed systems extracted with the introspection tools.
     - --
   * - `SysML2-server-api <https://github.com/CoreSenseEU/SysML2-server-api>`_
     - Dockerised local SysML v2 server and API pipeline.
     - Docker

ROS 2 instrumentation
*********************

.. list-table::
   :header-rows: 1
   :widths: 30 55 15

   * - Repository
     - Description
     - Install
   * - `coresense_instrumentation <https://github.com/CoreSenseEU/coresense_instrumentation>`_
     - Virtual drivers to activate, deactivate and monitor data flows, and an RViz plugin. See :ref:`instrumentation`.
     - Pixi, source

Testbeds
********

.. list-table::
   :header-rows: 1
   :widths: 30 55 15

   * - Repository
     - Description
     - Install
   * - `aerostack2 <https://github.com/aerostack2/aerostack2>`_
     - ROS 2 framework for autonomous aerial systems, used as the runtime platform in the inspection testbed. See `Aerostack2 documentation <https://aerostack2.github.io>`_.
     - apt, source
   * - `CoreSense4Home <https://github.com/CoreSenseEU/CoreSense4Home>`_
     - CoreSense implementation for RoboCup@Home (social testbed).
     - source
   * - `cs4home_hri_challenge <https://github.com/CoreSenseEU/cs4home_hri_challenge>`_
     - HRI challenge of the social testbed.
     - source
   * - `tiago_sw <https://github.com/CoreSenseEU/tiago_sw>`_
     - Open-source software for the PAL TIAGo robot used in the social testbed.
     - source, apt
   * - `collective_awareness_structure <https://github.com/CoreSenseEU/collective_awareness_structure>`_
     - Collective awareness for multi-robot systems built with Aerostack2 (inspection testbed).
     - Pixi, source
   * - `tb2_project <https://github.com/CoreSenseEU/tb2_project>`_
     - Simulation of the drone panel inspection testbed.
     - source
