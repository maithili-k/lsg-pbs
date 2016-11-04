
.. _pbs-jobs:

Login to the User Interface
...............
1. Login to the Life Science Grid (LSG) User Interface. We will login into the "kun" cluster located in Nijmegen:

  .. code-block:: console

     ssh -X homer@gb-ui-kun.els.sara.nl  # replace homer with your username 

2. Where are you? 

 .. code-block:: console

     pwd 
     
3. What are the contents of your home directory?
 .. code-block:: console

     ls
     
4. Go to the directory local-pbs-job
 .. code-block:: console

   cd local-pbs-job
   ls -l
    -rw-rw-r-- 1 maithilk maithilk   50 Oct 31 11:41 hello.sh
    drwxrwxr-x 2 maithilk maithilk   23 Oct 31 11:29 runfish
    -rwxr-xr-x 1 maithilk maithilk 8.3K Oct 31 11:29 runFish.py
    -rw-rw-r-- 1 maithilk maithilk  879 Oct 31 11:29 wrapper.sh

Run your first script
....................
     
5. Let's run your first script!
 .. code-block:: console

     ./hello.sh
  
It gives an error as you don't have the permission to execute it.

6. Change the permission and execute it
 .. code-block:: console

     chmod +x hello.sh 
     
7. Let's change the script to say hello 'your-name'
 .. code-block:: console

     nano hello.sh 

8. Run the script again. What does it say?





