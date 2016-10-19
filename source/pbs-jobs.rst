
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
     
   -rw-rw-r-- 1 maithilk maithilk 2644 Oct 19 11:28 fractals.c
   -rw-rw-r-- 1 maithilk maithilk   19 Oct 19 11:14 hello.sh
   -rw-rw-r-- 1 maithilk maithilk   70 Oct 19 11:25 wrapper.sh

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

     *editor* hello.sh 

8. Run the script again. What does it say?

Submit a job to the cluster
.................

9. Let's first compile the program
 .. code-block:: console
    
    cc fractals.c -o fractals 
    
10. What is in the file wrapper.sh?
 .. code-block:: console
    
    cat wrapper.sh

11. Submit the job to the cluster
 .. code-block:: console
  
  qsub wrapper.sh
  
  6401.gb-ce-kun.els.sara.nl
  
This command returns a jobID (e.g., here it is 6401) that can be used to monitor the progress of the job

12. Monitor the progress of your job 
 .. code-block:: console
  
  qstat 6401   # replace 6401 with your jobID
  
  Job ID                    Name             User            Time Use S Queue
  ------------------------- ---------------- --------------- -------- - -----
  6401.gb-ce-kun           wrapper.sh       maithilk        00:00:00 R medium 
  
  qstat -f 6401 # replace 6401 with your jobID, this will give more details 
  
13. Once the job is ready the status will be (or dont show this part and ask if anyone has a different output)
 .. code-block:: console
 
  qstat 6401
  
  qstat: Unknown Job Id Error 6401.gb-ui-kun.els.sara.nl

14. This suggests that the job is done. What is your output?
 .. code-block:: console
 
  ls
 
  -rw------- 1 maithilk maithilk      95  Oct 19 12:15 wrapper.sh.e653789
  -rw------- 1 maithilk maithilk     155  Oct 19 12:15 wrapper.sh.o653789
  -rw-rw-r-- 1 maithilk maithilk 15595245 Oct 19 12:15 output
  
15. What is in the wrapper.sh.e*** and wrapper.sh.o*** files?
 
16. Display the result of fractals run
 .. code-block:: console

  convert output "output.png"
  display output

Advanced functions
....................

17. Additional commands
 .. code-block:: console

  qstat -u homer  # replace homer with your username, lists your jobs

  qdel 6401       # replace 6401 with your jobID, cancels your submitted job

  qstat           # List all the running/queued jobs in the cluster

18. **Walltime** For how long will the sysem wait to run your job. Specify the maximum job walltime in hh:mm:ss
 .. code-block:: console
 
  PBS -l walltime=4:00:00 # the job will run 4h at maximum

**Local queues** On the LSG clusters you can find different queue types. 

=============== ===========================
Queue           Max. Walltime (hh:mm:ss)
=============== ===========================
express         00:30:00
infra           00:30:00
medium          36:00:00
long            72:00:00
=============== ===========================
This can be specified with the following command
 
 .. code-block:: console
   
   qsub -q long wrapper.sh # allow job to run for 72 hours
 

System commands

what if you have i/p o/p those examples
walltime: for how long will the system wait? etc





