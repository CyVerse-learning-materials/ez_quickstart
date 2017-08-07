|CyVerse logo|_

|Home_Icon|_
`Learning Center Home <http://learning.cyverse.org/>`_

*Advanced Installation of Docker*
=================================

*Docker-Compose install with Anaconda*
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1. Install `pip`

    ``sudo wget https://bootstrap.pypa.io/get-pip.py``

    ``python get-pip.py``

2. Change ownership of `/home/anaconda*`

    ``sudo chown ${USER}:iplant-everyone /home/anaconda*/ -R``

3. Install Docker-Compose

    ``sudo pip install docker-compose``

*Running Docker without sudo*
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1. Add the Docker group

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

