Types
=====



**property** ``$tType``
-----------------------

A specific characteristic of a `modelet <modelet.html>`_ or `engine <engine.html>`_. Multiple things can exhibit the same `property <property.html>`_.

.. admonition:: example

   - color: red 
   - age: 14 years

Source: ``properties.tff``

Relations
=========

.. _has_value:

**has_value** ( `property <#property>`_ > **$real** )
------------------------------------------------------------------------------

The value of a certain `property <#property>`_.

Source: ``properties.tff``

.. _datatype_of_p:

**datatype_of_property** ( `property <#property>`_ > `datatype <datatype.html>`_ )
-----------------------------------------------------------------------------------------------------------

The `datatype <datatype.html>`_ of a certain `property <#property>`_.

Source: ``properties.tff``

.. _is_property_of_m:

**is_property_of_modelet** (( `property <#property>`_ * `modelet <modelet.html>`_ ) > **$o** )
---------------------------------------------------------------------------------------------------------------------------------

Check if a `modelet <modelet.html>`_ is described by a certain `property <#property>`_.

Source: ``properties.tff``

.. _is_property_of_e:

**is_property_of_engine** (( `property <#property>`_ * `engine <engine.html>`_ ) > **$o** )
------------------------------------------------------------------------------------------------------------------------------

Check if an `engine <engine.html>`_ is described by a certain `property <#property>`_.

Source: ``properties.tff``
