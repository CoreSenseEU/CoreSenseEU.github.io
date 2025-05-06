Types
=====



**requirement** ``$tType``
--------------------------

A restriction on the `property <property.html>`_ values that a `template <template.html>`_ may enforce on a `modelet <modelet.html>`_.

Source: ``properties.tff``

Relations
=========

.. _datatype_of_p:

**datatype_of_requirement** ( `requirement <#requirement>`_ > `datatype <datatype.html>`_ )
--------------------------------------------------------------------------------------------------------------------

The `datatype <datatype.html>`_ of a certain `requirement <#requirement>`_.

Source: ``properties.tff``

.. _is_permissible:

**is_permissible** (( `requirement <#requirement>`_ * **$real** ) > **$o** )
---------------------------------------------------------------------------------------------------------------

Check if a value is *permissible* under a certain `requirement <#requirement>`_.

Source: ``properties.tff``

.. _is_part_of:

**is_part_of** (( `requirement <#requirement>`_ * `template <template.html>`_ ) > **$o** )
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Check if a `requirement <#requirement>`_ is part of a `template <template.html>`_.

Source: ``properties.tff``
