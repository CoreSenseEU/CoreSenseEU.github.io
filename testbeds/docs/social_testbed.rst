.. _social_testbed:

TB3: Social Testbed
*******************

The social testbed evaluates CoreSense in human-robot interaction, following the tasks of the RoboCup@Home competition: a PAL TIAGo robot interacts with people in a domestic environment. It has been developed by URJC and PAL Robotics, with a copy of the arena at the University of León (León@Home, a certified European Robotics League testbed), at URJC and at PAL.

The main demonstrator is the RoboCup@Home HRI Challenge: the robot receives a guest, describes and introduces the person, finds a seat and helps with a bag. It uses the following CoreSense software:

- `cs4home_architecture <https://github.com/CoreSenseEU/cs4home_architecture>`_: ROS 2 implementation of the CoreSense architecture (see :ref:`tutorial_cs4home`).
- `cs4home_hri_challenge <https://github.com/CoreSenseEU/cs4home_hri_challenge>`_: coordination of the cognitive modules for the HRI challenge.
- `cs4home_sound_module <https://github.com/CoreSenseEU/cs4home_sound_module>`_: auditory event detection and sound source localisation.
- `cs4home_vision_module <https://github.com/CoreSenseEU/cs4home_vision_module>`_: scene understanding and perception of contextual entities.
- `cs4home_person_tracker_module <https://github.com/CoreSenseEU/cs4home_person_tracker_module>`_: person tracking from camera and laser detections.
- `cs4home-explainability <https://github.com/CoreSenseEU/cs4home-explainability>`_: human-understandable explanations when failures, timeouts or unexpected situations occur.
- `CoreSense4Home <https://github.com/CoreSenseEU/CoreSense4Home>`_: behaviours and bringup for RoboCup@Home.
- `tiago_sw <https://github.com/CoreSenseEU/tiago_sw>`_: open-source software of the TIAGo robot.

The testbed is described in the public deliverables `D8.1 Social Testbed Concept and Requirements Specification <https://www.coresense.eu/doc/CS-024.pdf>`_ and D8.3 Social Testbed Implementation.
