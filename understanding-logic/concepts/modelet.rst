Types
=====



**modelet** ``$tType``
----------------------

Models a `phenomenon <phenomenon.html>`_ as the *thought* in the triangle of meaning. All modelets describe an instance of a `concept <concept.html>`_, have an `origin <origin.html>`_, and are modeled in a specific `formalism <formalism.html>`_.

-  `Concept <concept.html>`_: the *phenomenon* of the
   `modelet <modelet.html>`_, an instance of a class in the world model.
-  `Origin <origin.html>`_: the agent’s perspective on the *phenomenon*
-  `Formalism <formalism.html>`_: the representation of the *phenomenon*

Source: ``engines-and-modelets.tff``


**modelet_set** ``$tType``
--------------------------

Some particular set of `modelets <modelet.html>`_ which the reasoner has assembled. Used to collect the inputs to an `engine <engine.html>`_. 

.. admonition:: Example


   - {m1, m2, m3} 
   - {m2}
   - {}

Source: ``engines-and-modelets.tff``

Relations
=========

.. _modelet_models_concept:

**modelet_models_concept** ( `modelet <modelet.html>`_ > `phenomenon <phenomenon.html>`_ )
--------------------------------------------------------------------------------------------------------------

The `phenomenon <phenomenon.html>`_ symbolizing the *phenomenon* of a `modelet <modelet.html>`_. 

Source: ``engines-and-modelets.tff``

.. _formalism_of_modelet:

**formalism_of_modelet** ( `modelet <modelet.html>`_ > `formalism <formalism.html>`_ )
----------------------------------------------------------------------------------------------------------

The `formalism <formalism.html>`_ used by a `modelet <modelet.html>`_ to describe the *phenomenon*.

Source: ``engines-and-modelets.tff``

.. _modelet_creation_date:

**modelet_creation_date** ( `modelet <modelet.html>`_ > **$real** )
----------------------------------------------------------------------------------------

The date a `modelet <modelet.html>`_ was created.

.. admonition:: TODO

   The date is represented as a ``$real`` but we don’t make any assumptions about what that number represents. Unix time? time since last restart? seconds? This may be solved by integration with ``spacetime_point``.

Source: ``engines-and-modelets.tff``

.. _modelet_has_location:

**modelet_has_location** ( `modelet <modelet.html>`_ > `spacetime_point <spacetime_point.html>`_ )
----------------------------------------------------------------------------------------------------------------------

The time and spatial location a `modelet <modelet.html>`_ refers to. `Modelets <modelet.html>`_ may have a specific temporal scope or make an observation at a specific `spacetime_point <spacetime_point.html>`_.

Source: ``engines-and-modelets.tff``

.. _modelet_has_extent:

**modelet_has_extent** ( `modelet <modelet.html>`_ > `extent <extent.html>`_ )
--------------------------------------------------------------------------------------------------

The time and spatial `extent <extent.html>`_ a `modelet <modelet.html>`_ refers to. `Modelets <modelet.html>`_ may have an area/volume/duration of reference.

Source: ``engines-and-modelets.tff``

.. _modelet_has_representation_class:

**modelet_has_representation_class** ( `modelet <modelet.html>`_ > `representation_class <representation_class.html>`_ )
--------------------------------------------------------------------------------------------------------------------------------------------

The `representation_class <representation_class.html>`_ a `modelet <modelet.html>`_’s relation to its parents has after being created by an `engine <engine.html>`_. 

.. hint::
   
   This looks like it will turn out to be HOL.

Source: ``engines-and-modelets.tff``

.. _modelet_has_creator:

**modelet_has_creator** ( `modelet <modelet.html>`_ > `engine <engine.html>`_ )
---------------------------------------------------------------------------------------------------

The `engine <engine.html>`_ that created the `modelet <modelet.html>`_.

Source: ``engines-and-modelets.tff``

.. _is_in_modelet_set:

**is_in_modelet_set** (( `modelet <modelet.html>`_ * `modelet_set <modelet.html_set>`_ ) > **$o** )
-------------------------------------------------------------------------------------------------------------------------------

Check if a `modelet <modelet.html>`_ is a member of a `modelet_set <modelet.html_set>`_.

Source: ``engines-and-modelets.tff``
