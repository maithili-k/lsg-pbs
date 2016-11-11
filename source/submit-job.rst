Submit a job to the cluster
.................

1. Submit the job to the cluster
 .. code-block:: console
  
  qsub -q stud_queue wrapper.sh
  
  6402.gb-ce-kun.els.sara.nl
  
2. Monitor the progress of your job 
 .. code-block:: console
  
  qstat 6402   # replace 6402 with your jobID
  
  Job ID                    Name             User            Time Use S Queue
  ------------------------- ---------------- --------------- -------- - -----
  6402.gb-ce-kun           wrapper.sh       maithilk        00:00:00 R stud_queue 
  
3. Run the command
 .. code-block:: console
 
  qstat
  
What do you see? What does it mean?
  
4. Once the job is done what is your output?
 .. code-block:: console
 
  ls
  
  hello.sh
  hello.sh.e6401
  hello.sh.o6401
  runfish
  runFish.py
  wrapper.sh
  wrapper.sh.e6402
  wrapper.sh.o6402

5. The path to the software was not given correctly, so the job failed to run the example properly and generate the output. Uncomment the line no. X (remove the #), save the script and run the qsub command again
.. code-block:: console
  
  qsub -q stud_queue wrapper.sh

15. Display the result of your first job
 .. code-block:: console

    display PC1-2.png

In case this does not work, you can copy the file locally on your laptop and then view it. Open a new tab on your terminal  and type
 
 .. code-block:: console

  scp homer@gb-ui-kun.els.sara.nl:/home/homer/local-pbs-job/PC1-2.png .  # replace homer with your username
 
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






