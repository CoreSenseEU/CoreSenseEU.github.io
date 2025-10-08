





Relations
=========

.. _inputs_match:

**inputs_match** (( `modelet <modelet.html>`_ * `template <template.html>`_ ) > **$o** )
----------------------------------------------------------------------------------------

Check if a `modelet <modelet.html>`_ matches a `template <template.html>`_.

-  Check if they are `formally equivalent <#formally_equivalent>`_
-  Check if the `modelet <modelet.html>`_ contains *permissible* values
   for each of the `properties <property.html>`_ of `requirements <requirement.html>`_ of the `template <template.html>`_.

Source: ``engines-and-modelets.tff``, ``properties.tff``

.. _formally_equivalent:

**formally_equivalent** (( `template <template.html>`_ * `modelet <modelet.html>`_ ) > **$o** )
-----------------------------------------------------------------------------------------------

A `template <template.html>`_ and a `modelet <modelet.html>`_ share the same *phenomenon* and `formalism <formalism.html>`_.

Source: ``properties.tff``

.. _interfaces_match:

**interfaces_match** (( `modelet_set <modelet.rst#modelet_set>`_ * `template_set <template.rst#template_set>`_ ) > **$o** )
---------------------------------------------------------------------------------------------------------------------------

Check if all of the `templates <template.html>`_ in the `template_set <template.rst#template_set>`_ have a corresponding `modelet <modelet.html>`_ in the `modelet_set <modelet.rst#modelet_set>`_ with matching profile.

-  Check if they are `formally equivalent <#formally_equivalent>`_
-  Check if their `inputs match <#inputs_match>`_

Source: ``engines-and-modelets.tff``, ``properties.tff``

.. _exert:

**exert** (( `engine <engine.html>`_ * `modelet_set <modelet.rst#modelet_set>`_ * `modelet <modelet.html>`_ ) > **$o** )
------------------------------------------------------------------------------------------------------------------------

Exert an `engine <engine.html>`_ on a `modelet_set <modelet.rst#modelet_set>`_ to produce an output `modelet <modelet.html>`_. 

Source: ``engines-and-modelets.tff``

.. _exertable:

**exertable** (( `modelet_set <modelet.rst#modelet_set>`_ * `engine <engine.html>`_ ) > **$o** )
------------------------------------------------------------------------------------------------

A `modelet_set <modelet.rst#modelet_set>`_ can be exerted by an `engine <engine.html>`_ iff their `interfaces match <#interfaces_match>`_. 

Source: ``engines-and-modelets.tff``

.. _exertion:

**exertion** (( `engine <engine.html>`_ * `modelet_set <modelet.rst#modelet_set>`_ * `modelet <modelet.rst#modelet>`_ * `modelet_set <modelet.rst#modelet_set>`_ ) >  `modelet_set <modelet.rst#modelet_set>`_ )
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


The act of exerting an `engine <engine.html>`_ on a `modelet_set <modelet.rst#modelet_set>`_, resulting in a `modelet <modelet.html>`_, in defined state of knowledge, resulting in the addition of the output modelet to that state of knowledge. 

Source: ``understanding-calculus.tff``
