Types
=====



**engine** ``$tType``
---------------------

Does work within a **CoreSense** `agent <agent.html>`_ to produce `modelets <modelet.html>`_.

-  Takes multiple `modelets <modelet.html>`_ as an input `modelet_set <modelet.rst#modelet_set>`_
-  Uses semantic information to identify valid input modelet `formalisms <formalism.html>`_

   -  semantics could be external (part of the type definition) or internal (modeled within the `modelet <modelet.html>`_ itself)
-  Produces one output `modelet <modelet.html>`_

   -  May or may not impart semantic meaning to the output `modelet <modelet.html>`_
   -  May (re)define the output modelet `origin <origin.html>`_, `concept <concept.html>`_, or characteristics
-  Has `exertion <exertion.html>`_ characteristics

   -  e.g. time delay, resource usage, power consumption

.. admonition:: Example

   - DroneStateEngine (see tff/tests/test-wind-estimation.tff)

      - Input Model: 
 
         - Modelet

            - formalism: IMU.msg 
            - modelled concept: inertia 

         - Modelet:
         
            - formalism: NavSatFix.msg
            - modelled concept: geolocation
     
      - Output Modelet:
       
         - modelet:
            
            - formalism: DroneState.msg
            - modelled concept: drone_state

Source: ``engines-and-modelets.tff``

Relations
=========

.. _interface_of:

**interface_of** ( `engine <#engine>`_ > `template_set <template.rst#template_set>`_ )
--------------------------------------------------------------------------------------

An `engine <#engine>`_ requires a set of input `modelets <modelet.html>`_ which matches the `template_set <template.rst#template_set>`_.

Source: ``engines-and-modelets.tff``

.. _output_modelet_formalism:

**output_modelet_formalism** ( `engine <#engine>`_ > `formalism <formalism.html>`_ )
------------------------------------------------------------------------------------

The `formalism <formalism.html>`_ of an `engine <#engine>`_ output `modelet <modelet.html>`_.

Source: ``engines-and-modelets.tff``

.. _is_output_modelet_concept:

**is_output_modelet_concept** ( `engine <#engine>`_ > `phenomenon <phenomenon.html>`_ )
---------------------------------------------------------------------------------------

The `concept <concept.html>`_ of an `engine <#engine>`_ output `modelet <modelet.html>`_.

Source: ``engines-and-modelets.tff``

.. _output_property_of_e:

**output_property_of_engine** ( `engine <#engine>`_ > `property <property.html>`_ )
-----------------------------------------------------------------------------------

The `property <property.html>`_ an `engine <#engine>`_ imparts on its output `modelet <modelet.html>`_.

Source: ``properties.tff``

.. _engine_imparts_representation_class:

**engine_imparts_representation_class** ( `engine <#engine>`_ > `representation_class <representation_class.html>`_ )
---------------------------------------------------------------------------------------------------------------------

The `representation_class <representation_class.html>`_ an `engine <#engine>`_ imparts on its output `modelet <modelet.html>`_.

Source: ``engines-and-modelets.tff``
