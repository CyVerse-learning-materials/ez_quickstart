|CyVerse logo|_

|Home_Icon|_
`Learning Center Home <http://learning.cyverse.org/>`_

Install Popular Data Science Tools on Atmosphere Instances
============================================================

..
    #### Comment: Use short, imperative titles e.g. Upload and share data, uploading and
    sharing data ####

*Goal*
------

..
    Avoid covering upstream and downstream steps that are not explicitly and
    necessarily part of the tutorial - write or link to separate quick
    starts/tutorials for those parts

..
    #### Comment: A few sentences (50 words or less) describing the ultimate goal of the steps
    in this tutorial ####

----

.. toctree::
	:maxdepth: 2

	EZ Installation of Popular Data Scientist Tools <self>
  Installation of RStudio on an Atmosphere Instance <rstudio.rst>
  Advanced Installation of Docker <docker.rst>

..
	#### Comment: This tutorial can have multiple pages. The table of contents assumes
	you have an additional page called 'Step Two' with content located in 'step2.rst'
	Edit these titles and filenames as needed ####

..
    #### Comment: If you are using the TOC remove the 'summary', 'Additional information,
    help' and 'Fix or improve this tutorial' from all pages except the last page of the
    quickstart ####

-----

*Prerequisites*
---------------



Downloads, access, and services
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

*In order to complete this tutorial you will need access to the following services/software*


 .. list-table::
   :header-rows: 1

   * - Prerequisite
     - Preparation/Notes
     - Link/Download
   * - CyVerse account
     - You will need a CyVerse account to complete this exercise
     - `Register <https://user.cyverse.org/>`_
   * - Atmosphere access
     - You must have access to Atmosphere
     - `Request Access <https://user.cyverse.org/>`_

Platform(s)
~~~~~~~~~~~

*We will use the following CyVerse platform(s):*

 ..
   #### comment: delete any row not needed in this table ####

.. list-table::
    :header-rows: 1

    * - Platform
      - Interface
      - Link
      - Platform Documentation
      - Quick Start
    * - Atmosphere
      - Command line (ssh) and/or Desktop (VNC)
      - `Atmosphere <https://atmo.cyverse.org>`_
      - `Atmosphere Manual <https://wiki.cyverse.org/wiki/display/atmman/Atmosphere+Manual+Table+of+Contents>`_
      - `Guide <https://cyverse-atmosphere-guide.readthedocs-hosted.com/en/latest/>`__

Atmosphere Images
~~~~~~~~~~~~~~~~~

*In order to complete this quickstart you will need to have the following*

.. list-table::
    :header-rows: 1

    * - Atmosphere Image(s)
      - Link

    * - Only 'Featured' images have ``ez`` installed
      - `Atmosphere Featured Images <https://atmo.cyverse.org/application/images/search>`__


----


*Get Started*
-------------

*EZ Install (Jupyter, R, Python 2, Python 3)*
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



1. Jupyter notebooks with Python 3 (default)

	``ezj``

2. Jupyter notebooks with Python 2

	``ezj -2``

3. Jupyter notebooks with R Kernel

	``ezj -R`` or ``ezj -r``

4. After the installation, copy and paste the URL provided into your local computer's browser

	a. Open Firefox or Chrome on the local computer (your laptop or desktop you are working on)

	b. In a blank tab, copy and paste the URL provided by ``ezj`` at the end of the installation

	c. Leave the Atmosphere terminal running

	d. This has been tested on Firefox and Chrome

5. When you are done using the Jupyter Notebook

	a. Close out the browser tab with the Jupyter notebook interface

	b. Return to the Atmosphere and press: ``control + C``

	c. This will stop the Atmosphere instance from running Jupyter notebooks

*Start a new Jupyter session on a VM with EZ already installed*

1. Return to the Atmosphere instance and type ``ezj`` again!

	``ezj``
2. Copy and paste the URL into the browser just as before

*EZ Install Singularity*
~~~~~~~~~~~~~~~~~~~~~~~~~

1. Install Singularity

	``ezs``

You should see

	``* Updating ez singularity and installing singularity (this may take a few minutes, coffee break!)``

	``[sudo] password for YourCyVerseUserName:``

Wait for the installation to complete.

2. Test Singularity

	``singularity run shub://vsoch/hello-world``

*EZ Install Docker*
~~~~~~~~~~~~~~~~~~~~~~~~~~

1. Install Docker

	``ezd``

2. Test Docker

	note: You need to use ``sudo`` permissions with Docker. After using the ``sudo`` command, Atmosphere will ask you for your CyVerse password for security purposes.

	``sudo docker run hello-world``

----



*Next Steps:*
-------------

Some common next steps include:

1. `Installation of Rstudio on an Atmosphere Instance <rstudio.html>`_

2. `Advanced Docker Setup <docker.html>`_

----

Additional Information
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

..
    Short description and links to any reading materials

Search for an answer: `CyVerse Learning Center <http://learning.cyverse.org>`_ or `CyVerse Wiki <https://wiki.cyverse.org>`_

----

**Fix or improve this documentation**

- On Github: `<https://github.com/CyVerse-learning-materials/ez_quickstart>`_
- Send feedback: `Tutorials@CyVerse.org <Tutorials@CyVerse.org>`_

----

|Home_Icon|_
`Learning Center Home <http://learning.cyverse.org/>`__

.. |CyVerse logo| image:: ./img/cyverse_rgb.png
    :width: 500
    :height: 100
.. _CyVerse logo: http://learning.cyverse.org/
.. |Home_Icon| image:: ./img/homeicon.png
    :width: 25
    :height: 25
.. _Home_Icon: http://learning.cyverse.org/
