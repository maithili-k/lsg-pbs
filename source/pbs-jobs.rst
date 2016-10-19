
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
     ls
     
Run your first script
....................
     
5. Let's run your first script!
 .. code-block:: console

     ./hello.sh
     
6. Let's change the script to say hello 'your-name'
 .. code-block:: console

     *editor* hello.sh 

7. Run the script again. What does it say?

Submit a job to the cluster
.................

8. Let's compile a program and run it on the cluster
 .. code-block:: console
 
   ls -l

   -rw-r--r-- 1 homer homer fractals.c
   -rw-rw-r-- 1 homer homer hello.sh
   -rw-rw-r-- 1 homer homer wrapper.sh
   
9. Compile the program fractals.c
 .. code-block:: console
    
    cc fractals.c -o fractals 
    
10. What is inside the wrapper.sh
 .. code-block:: console
    
    cat wrapper.sh

11. Submit the job to the local cluster
 .. code-block:: console
  
  qsub wrapper.sh
  
  6401.gb-ce-kun.els.sara.nl

12. This command returns a jobID (e.g., here it is 6401) that can be used to monitor the progress of the job
 .. code-block:: console
  
  qstat 6401   # replace 6401 with your jobID
  
  Job ID                    Name             User            Time Use S Queue
  ------------------------- ---------------- --------------- -------- - -----
  6401.gb-ce-kun           wrapper.sh       maithilk        00:00:00 R medium 
  
13. Once the job is ready the status will be (or dont show this part and ask if anyone has a different output)
 .. code-block:: console
 
  qstat 6401
  
  qstat: Unknown Job Id Error 6401.gb-ui-kun.els.sara.n

14. You should have an output file "output". Display the result
 .. code-block:: console

  convert output "output.png"
  display output
 
15. System commands
the error output files location
what if you have i/p o/p those examples
walltime: for how long will the system wait? etc





