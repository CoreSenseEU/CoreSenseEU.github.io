.. _design:

CoreSense design
################

CoreSense is a hybrid cognitive architecture that gives robots the capability of *understanding*, the world and themselves, and of *awareness*, understanding in synchrony with perception. The theory behind it is described in the public deliverables `D1.3 Theory of Understanding <https://www.coresense.eu/doc/CS-050.pdf>`_ and `D1.4 Theory of Awareness <https://www.coresense.eu/doc/CS-060.pdf>`_. The terms used in the software follow the `CoreSense Ontology (CSO) <https://w3id.org/coresense/cso>`_.

Architecture subsystems
***********************

The architecture has three subsystems:

- **Runtime system**: a modular software structure, based on ROS 2, used to deploy, monitor and control the modules of the robot. It uses the instrumentation of the ROS 2 platform (see :ref:`instrumentation`).
- **Understanding core**: computes meanings on demand, when another subsystem asks for it, for example to generate an explanation for a user.
- **Awareness system**: a cognitive structure that continuously uses the understanding core on the flow of percepts. When the object of perception is the robot itself, it generates self-awareness.

The architecture is specified in `D2.2 Specification of the CoreSense Architecture <https://www.coresense.eu/doc/CS-059.pdf>`_, and its software assets are described in `D2.3 CoreSense Architecture <https://www.coresense.eu/doc/CS-098.pdf>`_.

Cognitive modules
*****************

A cognitive module is a set of ROS 2 nodes that performs a cognitive function. In the ROS 2 implementation of the architecture, `cs4home_architecture <https://github.com/CoreSenseEU/cs4home_architecture>`_, each module has five components, managed through ROS 2 lifecycle transitions:

- **Afferent**: receives information from the system or the environment.
- **Core**: performs the cognitive function.
- **Efferent**: sends the results to other modules or to the robot.
- **Meta**: provides information about the module.
- **Coupling**: coordinates the module with other modules.

.. code-block:: text

   information --> Afferent --> Core (cognitive function) --> Efferent --> other modules
                                  ^         ^
                                 Meta    Coupling

A master/flow mechanism coordinates several cognitive modules. The tutorial :ref:`tutorial_cs4home` shows how to build and run example modules.

Understanding system
********************

The understanding system, `coresense_understanding <https://github.com/CoreSenseEU/coresense_understanding>`_, generates strategies to obtain models with given properties. It combines existing models with model-modification skills, the *engines*. Each engine is a ROS 2 node, annotated with its inputs and outputs, whose skill is wrapped in a behaviour tree. The logic of the understanding core is in `understanding-logic <https://github.com/CoreSenseEU/understanding-logic>`_, and it uses the Vampire theorem prover through `coresense_vampire <https://github.com/CoreSenseEU/coresense_vampire>`_ and the knowledge base `triplestar_kb <https://github.com/CoreSenseEU/triplestar_kb>`_.

Engineering toolchain
*********************

CoreSense systems can be designed with model-based tools. See :ref:`toolchain_introduction`.
