.. include:: cyverse_rst_defined_substitutions.txt
|CyVerse_logo|_

|Home_Icon|_
`Learning Center Home <http://learning.cyverse.org/>`_

*Advanced Installation of Anaconda*
===================================

*Installing new packages * 
~~~~~~~~~~~~~~~~~~~~~~~~~~

Change ownership of the Anaconda installation directory to allow new software to be installed by the non-root user. 
  
    On Atmosphere: ``sudo chown $USER:iplant-everyone /opt/anaconda3 -R``
    
    On Jetstream: ``sudo chown $USER:root /opt/anaconda3 -R`` 
  
Use the ``conda install -c conda-forge package-name`` to add new packages.

----

**Fix or improve this documentation**

- Search for an answer:
  |CyVerse Learning Center|
- Ask us for help:
  click |Intercom| on the lower right-hand side of the page
- Report an issue or submit a change:
  |Github Repo Link|
- Send feedback: `Tutorials@CyVerse.org <Tutorials@CyVerse.org>`_



----

|Home_Icon|_
`Learning Center Home <http://learning.cyverse.org/>`_


.. |CyVerse logo| image:: ./img/cyverse_rgb.png
    :width: 500
    :height: 100
.. _CyVerse logo: http://learning.cyverse.org/
.. |Home_Icon| image:: ./img/homeicon.png
    :width: 25
    :height: 25
.. _Home_Icon: http://learning.cyverse.org/

