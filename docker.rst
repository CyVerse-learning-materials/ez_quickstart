|CyVerse logo|_

|Home_Icon|_
`Learning Center Home <http://learning.cyverse.org/>`_

*Advanced Installation of Docker*
=================================

*Docker-Compose Install* 
~~~~~~~~~~~~~~~~~~~~~~~~

   1. For instances without Anaconda install `pip`

    ``sudo wget https://bootstrap.pypa.io/get-pip.py``

    ``sudo python3 get-pip.py``

   2. For instances with Anaconda (ezj) change ownership of `/home/anaconda3`

    ``sudo chown ${USER}:iplant-everyone /home/anaconda3/ -R``

   3. Install Docker-Compose

    ``sudo pip3 install docker-compose``

*Running Docker without sudo*
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

   1. Check for and add the group `docker` (note: `docker` group should already exist)

    ``groupadd docker``

   2. Add user to group 

    ``sudo usermod -aG docker $USER``
    
   3. Close Terminal and reopen

   4. Test Docker without `sudo`

    ``docker run hello-world``


----

**Fix or improve this documentation**

- On Github: `<https://github.com/CyVerse-learning-materials/ez_quickstart>`_
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

