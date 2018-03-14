|CyVerse logo|_

|Home_Icon|_
`Learning Center Home <http://learning.cyverse.org/>`_

Install Popular Data Science Tools on Atmosphere or Jetstream Instances
=======================================================================

..
    #### Comment: Use short, imperative titles e.g. Upload and share data, uploading and
    sharing data ####

*Goal*
------
The `ez` command line program allows users to install popular data science packages such as Anaconda (Jupyter notebooks, Python 2/3, R), Docker, and Singularity with simple commands on any running Atmosphere or Jetstream instance.

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
   * - Atmosphere Access
     	- `Request Access <https://user.cyverse.org/>`_
   * - Jetstream Access
   	- `Request Access <https://portal.xsede.org/#/guest>`_ 

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

*In order to complete this quickstart you will need to have the following:*

.. list-table::
    :header-rows: 1

    * - A running Atmosphere instance using a featured image.
      - Notes
    * - `A running Atmosphere or Jetstream Image <https://atmo.cyverse.org/application/images/1420>`__


----

*Get Started*
-------------

*EZ Install Anaconda (Jupyter, Jupyter Hub, Jupyter Lab)*
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

  .. tip::

   `ez` allows an "easy" installation of `Anaconda <https://www.anaconda.com/>`_ based Jupyter notebooks or Jupyter Hub, Singularity, and Docker.
   
   This quickstart will cover specific commands for installing:

   - `Jupyter Notebooks <http://jupyter-notebook.readthedocs.io/en/latest/>`_
   - 'Jupyter Hub <http://jupyterhub.readthedocs.io/en/latest/>`_ 
   - `Singularity <http://singularity.lbl.gov/>`_
   - `Docker <https://www.docker.com/what-docker>`_

  1. Launch an `Atmosphere <https://atmo.cyverse.org/application/projects>`_ or `Jetstream <https://use.jetstream-cloud.org/application/projects>`_ instance and open the Web Shell.
  
  2. `Connect to Atmosphere via ssh <https://cyverse-atmosphere-guide.readthedocs-hosted.com/en/latest/step3.html#connect-to-atmosphere-instance-using-ssh>`_.

  3. From your connected session, you can install Jupyter using the following
     commands:

   - Jupyter notebooks with Python 3 (default)
      ``ezj``
   - Jupyter notebooks with Python 2
      ``ezj -2``
   - Jupyter notebooks with R Kernel
      ``ezj -R`` or ``ezj -r``
   - Jupyter Hub 
      ``ezjh``

*Connect to an Atmosphere instance running a Jupyter Notebook*
`````````````````````````````````````````````````````````````

  1. After the installation, you will be provided with a URL (e.g. `http ://128.196.65.162:8888/?token=2d6c40a7c8ee4b4933eaae5898101846bbfcd1e5d6bae37b` )
     copy and paste the URL provided into your local computer's browser.

    .. note::
     The Jupyter notebook is running as an active process in the foreground on your Atmosphere
     instance. If you disconnect from your Atmosphere terminal session, the Jupyter Notebook
     will terminate.

  2. To terminate your Jupyter Notebook, close the browser page with the Jupyter
     notebook interface. In your Atmosphere ssh session, press: ``control + C`` to
     terminate the Jupyter notebook.

*Start a new Jupyter session on a VM with EZ already installed*
````````````````````````````````````````````````````````````````

  1. Connect (ssh) into your running Atmosphere instance and type ``ezj``, this will restart
     a new Jupyter notebook. Connect to the notebook using the URL as in step 1 of the
     Connection instructions above.

*Install (new) JupyterLab*
~~~~~~~~~~~~~~~~~~~~~~~~~~

  1. Complete the installation of Jupyter notebooks as above. 
  
  2. Change ownership of the Anaconda installation to allow new software to be installed by the non-root user. 
  
  On Atmosphere:
  ``sudo chown $USER:iplant-everyone /home/anaconda3 -R``
  
  On Jetstream:
  ``sudo chown $USER:root /home/anaconda3 -R`` 
  
  3. Install Jupyter Lab *Beta*
  ``conda install -c conda-forge jupyterlab``
  
  3. Determine the version of Jupyter notebook installed. 
  ``jupyter --version``


*EZ Install Singularity*
~~~~~~~~~~~~~~~~~~~~~~~~~

  1. `Connect to Atmosphere via ssh`_.

  2. From your connected session, you can install Singularity using the following
     command:
     ``ezs``

   You should see

    .. code:: bash

      Updating ez singularity and installing singularity (this may take a few minutes, coffee break!)
      [sudo] password for YourCyVerseUserName:

   Wait for the installation to complete.

  3. Test Singularity

    ``singularity run shub://vsoch/hello-world``

*EZ Install Docker*
~~~~~~~~~~~~~~~~~~~~~~~~~~

 1. `Connect to Atmosphere via ssh`_.

 2. From your connected session, you can install Docker using the following
    command:

    ``ezd``

 3. Test Docker

    ``sudo docker run hello-world``

 .. note::

    You need to use sudo permissions with Docker. After using the sudo command,
    Atmosphere will ask you for your CyVerse password for security
    purposes. You can remove the need to use ``sudo`` with Docker commands in the `Advanced Docker Setup <docker.html>`_ section. 

----

*Next Steps:*
-------------

Some common next steps include:

1. `Installation of RStudio on an Atmosphere Instance <rstudio.html>`_

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
