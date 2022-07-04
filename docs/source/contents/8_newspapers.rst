==============
Newspaper Work
==============

-----
About
-----

Newspaper works are perhaps our most complex worktype. Unlike books and compound objects, newspapers have a hierarchical
structure that starts with a title, breaks down into volumes, and further down into issues. The date of publication and
access to OCR data via METS / ALTO are critical to the viewing experience.

For newspaper works, the title, volume, and issue should all be represented as an :code:`ore:Aggregation`. While we
believe it is reasonable to treat both titles and volumes as :code:`pcdm:Collection` s, our research shows that experts
believe these should be :code:`pcdmworks:Work` s or :code:`pcdm:Object` s. We are open to either and feel we should do
what is easiest. An issue should be a :code:`pcdmworks:Work` and pages within the issue should be :code:`pcdm:Object` s.
The METS file should be associated with the issue and the ALTO files should be associated with the page.  Since pages
have a specific order, they should be represented by :code:`ore:Proxy` s.

For IIIF, The title and volume should be represented by a IIIF collection. The issue should be a manifest with each page
serving as a canvas. The IIIF cookbook suggests that Alto should be represented by a :code:`seeAlso` property on the '
canvas. It also suggests the content of the METS / ALTO should be represented by a list of annotations in the
annotations property on each canvas with targets to the specific regions on the canvas and a motivation of
:code:`supplementing`.

Any files in a fileset that are not admin only or restricted should be available for download.

All files / filesets may have restrictions that prohibit view / access.

-------------------
Metadata Properties
-------------------

Descriptive Properties
======================

Descriptive properties are described in our
`vendor supplied MAP <https://docs.google.com/spreadsheets/d/1_0QVbQU_wj3ITUih5dGPGkWHN0QyhGO9hKSf6rXwKPc/edit#gid=0>`_.

Structural Properties
=====================

Suggested structure for a book is described here.

.. literalinclude:: ../fixtures/newspaper.ttl
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

All newspaper issues should be displayed in a IIIF viewer like Universal Viewer with a :code:`behavior` of :code:`paged`
on the manifest. The viewer should provide pan and zoom and ideally annotations on the correct portion of the canvas
derived from the METS / ALTO.

One of the important features of Newspapers is the publication date which can allow the user to navigate issues by the
date they were published. To achieve this, the :code:`navDate` property should be added both to the items in a
collection and also in the issue manifest. This allows viewers to present date-based navigation for Newspaper
collections.

The :code:`pcdmuse:IntermediateFile` should always be represented in the viewer.

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

.. figure:: ../images/clemson_location.png
    :alt: Location-based Example 4

If possible, we would also like our location information to be shared as a :code:`navPlace` extension in our IIIF
manifests.

----------------
Interoperability
----------------

OAI-PMH
=======

Like other work types, newspaper issues should be represented by an OAI-PMH record based on our metadata application
profile.  The work should be a record in an OAI set for each corresponding collection to which the work belongs. The
title and volume should both be an OAI-PMH set with records for each issue.

Page works should not be represented by an OAI-PMH record.

IIIF Image
==========

All pages should be served by a IIIF image service that adheres to at least IIIF Image API 2.1.1 that supports most
features described in `5.3 profile description <https://iiif.io/api/image/2.1/#profile-description>`_. As part of work
type negotiation, we would like to know any features that the IIIF Image service does not support.

IIIF Presentation v3
====================

All newspapers should have a corresponding IIIF presentation v3 manifest that allows the object to be shared and remixed
in other projects. This includes title, volume, and issue.

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
