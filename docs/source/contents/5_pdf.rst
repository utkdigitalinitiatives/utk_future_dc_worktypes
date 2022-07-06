========
PDF Work
========

-----
About
-----

PDF works are works where the primary fileset(s) are PDFs.  PDFs should minimally display something that allows the item
to be opened in a new tab or with the PDF.js viewer.

A PDF may also be converted on demand into a set of images making up each canvas. After that, the work will be displayed
in a IIIF viewer on the work page.

The PDF work's main file is both a :code:`pcdmuse:PreservationFile` and a :code:`pcdmuse:IntermediateFile` s. The work
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

The suggested structure of an image work with a :code:`pcdmuse:IntermediateFile` and :code:`pcdmuse:PreservationFile`.

.. literalinclude:: ../fixtures/pdf.ttl
    :language: turtle
    :linenos:

Technical Properties
====================

Technical properties are identified and listed in our
`metadata application profile <https://docs.google.com/spreadsheets/d/1_0QVbQU_wj3ITUih5dGPGkWHN0QyhGO9hKSf6rXwKPc/edit#gid=0>`_
in the files tab.