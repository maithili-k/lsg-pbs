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
  
4. Once the job is ready what is your output?
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

5. What does the wrapper.sh.e** file say?

6. The path to the software was not given correctly, so the job failed to run the example properly and generate the output. Uncomment the line no. X (remove the #), save the script and run the qsub command again

 .. code-block:: console

   qsub -q stud_queue wrapper.sh
   
7. Now check the status of the job with the new jobID
 
8. Display the result of your first job
 .. code-block:: console

    display PC1-2.png

In case this does not work, you can copy the file locally on your laptop and then view it. Open a new tab on your terminal  and type
 
 .. code-block:: console

  scp homer@gb-ui-kun.els.sara.nl:/home/homer/local-pbs-job/PC1-2.png .  # replace homer with your username
 
