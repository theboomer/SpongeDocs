======================
Working with Optionals
======================

TODO:

Basic Usage
===========

* What ``Optional<T>`` means: a value that may or may not be there, meaning that your plugin has to handle both cases somehow.
* Why you should call ``Optional#get()`` very carefully: throwing hard-to-debug errors, essentially lifting NullPointerException into a NoSuchElementException
* Using ``Optional#orElse`` and ``Optional#orElseThrow``: orElse for a default value, orElseThrow to throw a descriptive exception that you should handle later

The standard pattern of:

.. code-block:: java

 if (opt.isPresent()) {
  T value = opt.get();
 } else {
   // handle failure
 }

Advanced Usage
==============

* Using Optional#ifPresent: Only do something if it exists, no errors otherwise
* Using Optional#flatMap to chain optionals: useful especially with Data API, you can use this to chain an optional value with methods that return additional methods, i.e. opt.flatMap(value -> value.getData(SomeData.class))
* Constructing your own optionals: using Optional.empty() for empty, Optional.of for present, and Optional.ofNullable to lift a null into an Optional
