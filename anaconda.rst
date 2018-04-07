# Installing new packages in Anaconda

Change ownership of the Anaconda installation directory to allow new software to be installed by the non-root user. 
  
    On Atmosphere: ``sudo chown $USER:iplant-everyone /opt/anaconda3 -R``
    
    On Jetstream: ``sudo chown $USER:root /opt/anaconda3 -R`` 
  
