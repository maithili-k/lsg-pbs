
.. _pbs-jobs:

Login to the User Interface
...............
1. Open a shell and login to the Life Science Grid (LSG) User Interface with the following command. We will login into the "kun" cluster located in Nijmegen:

  .. code-block:: console

     ssh -X stud**@gb-ui-kun.els.sara.nl  # replace ** with the number at the end of your username 

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
   
   
You will see the output 

 .. code-block:: console
 
    -rw-rw-r-- 1 maithilk maithilk   50 Oct 31 11:41 hello.sh
    drwxrwxr-x 2 maithilk maithilk   23 Oct 31 11:29 runfish
    -rwxr-xr-x 1 maithilk maithilk 8.3K Oct 31 11:29 runFish.py
    -rw-rw-r-- 1 maithilk maithilk  879 Oct 31 11:29 wrapper.sh

Run your first script
....................
     
5. Let's run your first script!
 .. code-block:: console

     ./hello.sh
  
6. Let's change the script to say hello 'your-name'
 .. code-block:: console

     nano hello.sh 

7. Run the script again. What does it say?

8. So shall we run the same example on the cluster?

 .. code-block:: console
  
  qsub -q stud_queue wrapper.sh
  
 .. code-block:: console 
 
  6401.gb-ce-kun.els.sara.nl
  
This command returns a jobID (e.g., here it is 6401) that can be used to monitor the progress of the job.

9. Monitor the progress of your job 
 .. code-block:: console
  
  qstat 6401   # replace 6401 with your jobID
  
  Job ID                    Name             User            Time Use S Queue
  ------------------------- ---------------- --------------- -------- - -----
  6401.gb-ce-kun           wrapper.sh       maithilk        00:00:00 R stud_queue 
  
  qstat -f 6401 # replace 6401 with your jobID, this will give more details 
  
10. Once the job is ready the status will be:
 .. code-block:: console
 
  qstat 6401
  
  qstat: Unknown Job Id Error 6401.gb-ui-kun.els.sara.nl

14. This suggests that the job is done. What is your output?
 .. code-block:: console
  
  ls
  
  hello.sh
  runfish
  runFish.py
  wrapper.sh
  hello.sh.e6401
  hello.sh.o6401





