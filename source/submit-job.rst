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
  6401.gb-ce-kun           wrapper.sh       maithilk        00:00:00 R stud_queue 
  
  qstat -f 6401 # replace 6401 with your jobID, this will give more details 
  
12. Run the command
 .. code-block:: console
 
  qstat
  
What do you see? What does it mean?
  
13. Once the job is ready the status will be:
 .. code-block:: console
 
  qstat 6401
  
  qstat: Unknown Job Id Error 6401.gb-ui-kun.els.sara.nl

14. This suggests that the job is done. What is your output?
 .. code-block:: console
 
  ls
  
  hello.sh
  PC1-2.png
  runfish
  runFish.py
  wrapper.sh
  wrapper.sh.e6401
  wrapper.sh.o6401
 
15. Display the result of your first job
 .. code-block:: console

    display PC1-2.png

In case this does not work, you can copy the file locally on your laptop and then view it. Open a new tab on your terminal  and type
 
 .. code-block:: console

  scp homer@gb-ui-kun.els.sara.nl:/home/homer/local-pbs-job/PC1-2.png .  # replace homer with your username
 
