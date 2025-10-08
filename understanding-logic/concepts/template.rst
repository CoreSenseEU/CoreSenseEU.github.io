Types
=====



**template** ``$tType``
-----------------------

Describes the features that a single `modelet <modelet.html>`_ should have for an `engine <engine.html>`_ to accept it as input.

-  a semantic function signature
-  `properties <property.html>`_ and `requirements <requirement.html>`_ of `modelets <modelet.html>`_ 

Source: ``engines-and-modelets.tff``


**template_set** ``$tType``
---------------------------

Some particular set of `templates <template.html>`_ which describe the inputs to an `engine <engine.html>`_.

.. admonition:: Example 

   - {t1, t2, t3} 
   - {t2} 
   - {}

Source: ``engines-and-modelets.tff``

Relations
=========

.. _template_has_concept_requirement:

**template_has_concept_requirement** ( `template <#template>`_ > `concept <concept.html>`_ )
---------------------------------------------------------------------------------------------------------------------

The `concept <concept.html>`_ symbolizing the *phenomenon class* of a `template <template.html>`_.

Source: ``engines-and-modelets.tff``

.. _template_formalism_requirement:

**template_formalism_requirement** ( `template <#template>`_ > `formalism <formalism.html>`_ )
-----------------------------------------------------------------------------------------------------------------------

The `formalism <formalism.html>`_ this `template <#template>`_ expects the *phenomenon* to be described by.

Source: ``engines-and-templates.tff``

.. _template_has_location_requirement:

**template_has_location_requirement** ( `template <#template>`_ > `spacetime_point <spacetime_point.html>`_ )
--------------------------------------------------------------------------------------------------------------------------------------

The time and spatial location a `template <#template>`_ refers to. A `template <template.html>`_ may have a specific temporal scope or expect an observation at a specific `spacetime_point <spacetime_point.html>`_.

Source: ``engines-and-modelets.tff``

.. _template_has_extent_requirement:

**template_has_extent_requirement** ( `template <#template>`_ > `extent <extent.html>`_ )
------------------------------------------------------------------------------------------------------------------

The time and spatial `extent <extent.html>`_ a `template <#template>`_ covers. A `template <#template>`_ may expect an area/volume/duration of reference.

Source: ``engines-and-modelets.tff``

.. _template_has_creator_requirement:

**template_has_creator_requirement** ( `template <#template>`_ > `engine <engine.html>`_ )
-------------------------------------------------------------------------------------------------------------------

The `engine <engine.html>`_ a `template <#template>`_ requires a `modelet <modelet.html>`_ to have been created by.

Source: ``engines-and-modelets.tff``

.. _is_in_template_set:

**is_in_template_set** (( `template <#template>`_ * `template_set <#template_set>`_ ) > **$o** )
------------------------------------------------------------------------------------------------------------------------------------

Check if a `template <#template>`_ is a member of a `template_set <#template_set>`_.

Source: ``engines-and-modelets.tff``
