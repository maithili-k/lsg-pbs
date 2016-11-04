Submit a job to the cluster
.................

9. What is in the file wrapper.sh?
 .. code-block:: console
    
    cat wrapper.sh

10. Submit the job to the cluster
 .. code-block:: console
  
  qsub -q stud_queue wrapper.sh
  
  6401.gb-ce-kun.els.sara.nl
  
This command returns a jobID (e.g., here it is 6401) that can be used to monitor the progress of the job.

11. Monitor the progress of your job 
 .. code-block:: console
  
  qstat 6401   # replace 6401 with your jobID
  
  Job ID                    Name             User            Time Use S Queue
  ------------------------- ---------------- --------------- -------- - -----
  6401.gb-ce-kun           wrapper.sh       maithilk        00:00:00 R medium 
  
  qstat -f 6401 # replace 6401 with your jobID, this will give more details 
  
12. Once the job is ready the status will be:
 .. code-block:: console
 
  qstat 6401
  
  qstat: Unknown Job Id Error 6401.gb-ui-kun.els.sara.nl

14. This suggests that the job is done. What is your output?
 .. code-block:: console
 
  ls
  
  -rw-rw-r-- 1 maithilk maithilk     50 Oct 31 11:41 hello.sh
  -rw-rw-r-- 1 maithilk maithilk 131479 Oct 31 13:10 PC1-2.png
  drwxrwxr-x 2 maithilk maithilk     23 Oct 31 11:29 runfish
  -rwxr-xr-x 1 maithilk maithilk   8456 Oct 31 13:10 runFish.py
  -rw-rw-r-- 1 maithilk maithilk    879 Oct 31 11:29 wrapper.sh
  -rw------- 1 maithilk maithilk   2355 Oct 31 13:10 wrapper.sh.e6401
  -rw------- 1 maithilk maithilk    180 Oct 31 13:10 wrapper.sh.o6401
 
15. What is in the wrapper.sh.e*** and wrapper.sh.o*** files?

16. Display the result of fractals run
 .. code-block:: console

  display PC1-2.png

Advanced functions
....................

17. Additional commands
 .. code-block:: console
 
  qstat -f 6401   # Replace 6401 with your jobID, get details of the jobID 6401

  qstat -u homer  # Replace homer with your username, lists your jobs

  qdel 6401       # Replace 6401 with your jobID, cancels your submitted job

  qstat           # List all the running/queued jobs in the cluster
  
  pbsnodes        # List all running jobs per worker node and core

18. **Walltime** For how long will the sysem wait to run your job? Specify the maximum job walltime in hh:mm:ss in wrapper.sh
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

19. Specify the number of cores to be allocated for your job
 .. code-block:: console
   
  PBS -l nodes=1:ppn=2  # asks two cores on a single node






