====================
Text Representations
====================

``TextRepresentation``\ s provide a convenient way to serialize and de-serialize ``Text`` instances. There are three
applicable formats:

.. toctree::
    :maxdepth: 2
    :titlesonly:

    legacy
    xml
    json

The ``org.spongepowered.api.text.Texts`` class provides three methods for accessing the respective ``TextRepresentation``\ s:

* ``Texts#legacy``
* ``Texts#xml``
* ``Texts#json``

Working with TextRepresentations
================================

Serializing Text
~~~~~~~~~~~~~~~~

To serialize a ``Text`` object, simply use the ``TextRepresentation#to`` method, specifying the appropriate ``Text``
object as the first parameter. Optionally, specify a ``java.util.Locale`` as the second argument.

Deserializing to Text
~~~~~~~~~~~~~~~~~~~~~

To deserialize a ``String`` into its representing ``Text`` object, simply use the ``TextRepresentation#from`` method,
specififying the input ``String`` as the only argument. If the input is incorrectly formatted, a ``TextMessageException``
will be thrown. Alternatively, use the ``TextRepresentation#fromUnchecked`` method to deserialize without any exceptions.
If there is an error, the raw input will be returned in the form of a ``Text`` object
