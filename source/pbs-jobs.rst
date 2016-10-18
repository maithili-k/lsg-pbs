
.. _pbs-jobs:

Login to the User Interface (UI)
...............
1. Log in to the :abbr:`LSG (Life Science Grid)` User Interface. We will login into the "kun" cluster located in Nijmegen:

  .. code-block:: console

     ssh -X homer@gb-ui-kun.els.sara.nl  # replace homer with your username 

2. Where are you? 

 .. code-block:: console

     pwd 
     
3. What are the contents of your home directory?
 .. code-block:: console

     ls
     
4. Go to the directory local-job
 .. code-block:: console

     cd local-job
     ls
     
Run your first script
....................
     
5. Lets run your first script!
 .. code-block:: console

     ./hello.sh
     
6. Lets change the script to sat hello your-name
 .. code-block:: console

     *editor* hello.sh 

7. Run the script again. What does it say?

8. Lets compile a program and run it on the cluster
 .. code-block:: console
 
   ls -l

   -rw-r--r-- 1 homer homer fractals.c
   -rw-rw-r-- 1 homer homer hello.sh
   -rw-rw-r-- 1 homer homer wrapper.sh
   
9. Compile the program fractals.c
 .. code-block:: console
    
    cc fractals.c -o fractals 

Submit a job to the cluster
.................
    
10. Submit the job to the local cluster:


