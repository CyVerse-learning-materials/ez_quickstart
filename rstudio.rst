.. include:: cyverse_rst_defined_substitutions.txt
|CyVerse_logo|_

|Home_Icon|_
`Learning Center Home <http://learning.cyverse.org/>`_


*RStudio-Server install with Anaconda*
======================================

*Setting up RStudio-Server with the `ezj -R` function on Atmosphere*
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Recently we set up a `ez` script which is executed in the terminal or web shell to install Anaconda3 with Jupyter Notebook. One of the features is to install R kernel with Jupyter. It also installs `r-essentials <https://anaconda.org/r/r-essentials>`_ with numerous common R packages.

 1. Be sure to run `ezj -R` first. Reference documentation above if you have not. To set up RStudio-Server with the `conda` installation of R you need to set up the bash profile.

   - Add `anaconda3` to your path
   ``export PATH="/opt/anaconda3/bin:$PATH"``

   - Change ownership of the /opt/anaconda3/ directory
   ``sudo chown ${USER}:iplant-everyone /opt/anaconda3/ -R``

   - Add a path to your `~/.bash_profile`:
   ``echo "export RSTUDIO_WHICH_R='/opt/anaconda3/bin/R'" >> ~/.bash_profile``

 .. note::
    You will need to exit and restart your terminal for these to take effect

 2. Install RStudio-Server using the `latest version <https://www.rstudio.com/products/rstudio/download-server/>`_

 .. Ubuntu::
   - In a terminal, reset the symbolic link for `libfortran.so`:
   ``sudo ln -s /usr/lib/x86_64-linux-gnu/libgfortran.so.3 /usr/lib/libgfortran.so``

   - Install Dependencies
   ``sudo apt-get install gdebi-core g++``

   - Change to the `/opt` folder
   ``cd /opt``

   ``sudo wget https://download2.rstudio.org/rstudio-server-1.0.153-amd64.deb``

   ``sudo gdebi -n rstudio-server-1.0.153-amd64.deb``

 .. Centos::

   ``cd /opt``

   ``sudo wget https://download2.rstudio.org/rstudio-server-rhel-1.0.153-x86_64.rpm``

   ``sudo yum install --nogpgcheck rstudio-server-rhel-1.0.153-x86_64.rpm``

 .. note::
    This will fail on the first try:

::

   user_name@128:/home$ sudo gdebi rstudio-server-1.0.143-amd64.deb
   Reading package lists... Done
   Building dependency tree
   Reading state information... Done
   Reading state information... Done

   RStudio Server
   RStudio is a set of integrated tools designed to help you be more productive with R. It includes a console, syntax    highlighting editor that supports direct code execution, as well as tools for plotting, history, and workspace management.
   Do you want to install the software package? [y/N]:y
   (Reading database ... 136874 files and directories currently installed.)
    Preparing to unpack rstudio-server-1.0.143-amd64.deb ...
    Unpacking rstudio-server (1.0.143) over (1.0.143) ...
    Setting up rstudio-server (1.0.143) ...
    useradd: user 'rstudio-server' already exists
    groupadd: group 'rstudio-server' already exists
    rsession: no process found
    Created symlink from /etc/systemd/system/multi-user.target.wants/rstudio-server.service to /etc/systemd/system/rstudio- server.service.
    Job for rstudio-server.service failed because the control process exited with error code. See "systemctl status rstudio- server.service" and "journalctl -xe" for details.
    ● rstudio-server.service - RStudio Server
    Loaded: loaded (/etc/systemd/system/rstudio-server.service; enabled; vendor preset: enabled)
    Active: active (running) since Sat 2017-05-13 09:30:40 MST; 13ms ago
      Process: 2226 ExecStop=/usr/bin/killall -TERM rserver (code=exited, status=1/FAILURE)
      Process: 2233 ExecStart=/usr/lib/rstudio-server/bin/rserver (code=exited, status=0/SUCCESS)
     Main PID: 2236 (rserver)
     Tasks: 3
     Memory: 824.0K
       CPU: 10ms
    CGroup: /system.slice/rstudio-server.service
            └─2236 /usr/lib/rstudio-server/bin/rserver

    May 13 09:30:40 xxx.xxx.xx.xxx systemd[1]: rstudio-server.service: Service hold-off time over, scheduling restart.
    May 13 09:30:40 xxx.xxx.xx.xxx systemd[1]: Stopped RStudio Server.
    May 13 09:30:40 xxx.xxx.xx.xxx systemd[1]: Starting RStudio Server...
    May 13 09:30:40 xxx.xxx.xx.xxx systemd[1]: Started RStudio Server.
    May 13 09:30:40 xxx.xxx.xx.xxx rserver[2236]: ERROR Unable to find an installation of R on the system (which R didn't return  va...pp:472
    May 13 09:30:40 xxx.xxx.xx.xxx systemd[1]: rstudio-server.service: Main process exited, code=exited, status=1/FAILURE
    Hint: Some lines were ellipsized, use -l to show in full.

3. Modify `/etc/rstudio/rserver.conf`

   ``sudo sh -c 'echo "rsession-which-r=/opt/anaconda3/bin/R" >> /etc/rstudio/rserver.conf'``

4. Restart RStudio-Server

   ``sudo rstudio-server start``

5. Log into RStudio-Server

   - Copy the IP address for the VM from the Atmosphere browser window.
   - Paste the IP address into a new browser window
   - add `:8787` port # to the IP address
   - Log in using your CyVerse Username and Password.

*Installing Packages for R and RStudio-Server*
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 .. note::
    Because we are using Anaconda3, it is suggested that you use `conda` to install your R packages from a terminal
 ..

 Examples

   ``conda install -c r r-raster``

   ``conda install -c conda-forge gdal``

..
    #### Comment: A numbered list of steps go here ####

----

*Summary*
~~~~~~~~~
This documentation is intended for use with CyVerse `Atmosphere <http://atmo.cyverse.org>`_ featured images. It has been tested on Ubuntu 16.04 and Centos 6.8 images.

..

Additional information, help
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

..
    Short description and links to any reading materials





----

**Fix or improve this documentation**

- Search for an answer:
  |CyVerse Learning Center|
- Ask us for help:
  click |Intercom| on the lower right-hand side of the page
- Report an issue or submit a change:
  |Github Repo Link|
- Send feedback: `Tutorials@CyVerse.org <Tutorials@CyVerse.org>`_



-------------------------------------

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
