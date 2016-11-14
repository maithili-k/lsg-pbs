Advanced functions
....................

1. Additional commands
 .. code-block:: console
 
  qstat -f 6401   # Replace 6401 with your jobID, get details of the jobID 6401

  qstat -u homer  # Replace homer with your username, lists your jobs

  qdel 6401       # Replace 6401 with your jobID, cancels your submitted job

  qstat           # List all the running/queued jobs in the cluster
  
  pbsnodes        # List all running jobs per worker node and core

2. **Walltime** For how long will the sysem wait to run your job? Specify the maximum job walltime in hh:mm:ss in wrapper.sh
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

3. Specify the number of cores to be allocated for your job. What will this do?
 .. code-block:: console
   
  PBS -l nodes=1:ppn=2  # asks two cores on a single node
  
4. Where is the software installed? Is it local on your cluster or elsewhere? Where is the input dataset?
