============
Generic Work
============

-----
About
-----

Generic works are where the primary fileset(s) are binary with no complex expectations for user experience or viewer in
the browser. Instead, the primary purpose of this work type is to preserve and make available to users binary file types
such as WARCs or born digital objects.

The generic work will only ever have `pcdmuse:PreservationFile` files and never `pcdmuse:IntermediateFile`s. The work
may have a curated thumbnail or a thumbnail represented by the work type.

All filesets may have restrictions that prohibit view / access.

-------------------
Metadata Properties
-------------------

Descriptive Properties
======================

Descriptive properties are described in our
`vendor supplied MAP <https://docs.google.com/spreadsheets/d/1_0QVbQU_wj3ITUih5dGPGkWHN0QyhGO9hKSf6rXwKPc/edit#gid=0>`_.

Structural Properties
=====================

The structure of a generic work is very basic and described below.

.. literalinclude:: ../fixtures/generic.ttl
    :language: turtle
    :linenos:

Technical Properties
====================

Technical properties are identified and listed in our
`metadata application profile <https://docs.google.com/spreadsheets/d/1_0QVbQU_wj3ITUih5dGPGkWHN0QyhGO9hKSf6rXwKPc/edit#gid=0>`_
in the files tab.

------------------
Viewing Experience
------------------

IIIF Viewer
===========

No IIIF manifest should represent a generic work and thus no viewer.

Location-based Viewing
======================

Our metadata currently includes cartographic and coordinate information so that the metadata record can be easily intermixed with a location-based viewer. An item should not be playable from this view, but it should pop out into a new window. We also include a URI that points at a Geonames object that includes this same information.

If needed, we can continue to store cartographic and coordinate information in a separate field to make this easy.

Some sample location-based display might be:

.. figure:: ../images/location_based_1.png
    :alt: Location-based Example 1

.. figure:: ../images/location_based_2.png
    :alt: Location-based Example 2

.. figure:: ../images/location_based_3.png
    :alt: Location-based Example 3

If possible, we would also like our location information to be shared as a `navPlace` extension in our IIIF manifests.

Rights Viewing
==============

While we store our rights as uris (see metadata application profile), we’d like these statements to be actionable and
render the appropriate badge and usage information to the user.

File Viewer
===========

Users should be able to easily download the primary filesets.

If a fileset is only a `pcdm:PreservationFile` it should never be publicly visible.

.. figure:: ../images/file_download.png
    :alt: File Download Example

----------------
Interoperability
----------------

OAI-PMH
=======

Like other work types, generic works should be represented by an OAI-PMH record based on its metadata application
profile.  The work should be a record of an OAI set for each corresponding collection to which the object belongs. Our
metadata application profile should have a rule that states which field values should be remixed to OAI-PMH for a given
metadata format (simple dublin core, dcterms).

-------
Bulkrax
-------

Import
======

Like all work types, images should be importable according to our Metadata Application Profile via Bulkrax import using
CSV and XXXXXXX file storage solution.

Export
======

In addition to import functionality, images should have a variety of export options including the ability to export only
filesets related to preservation for easy transfer to Chronopolis.  Those filesets should be:

* :code:`pcdmuse:PreservationFile`

---------
Analytics
---------

------------
Restrictions
------------

Like other work types, video works may have restrictions at the work and fileset / file level.

------------
For UTK Only
------------

Migration Notes
===============
