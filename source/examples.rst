.. _examples:

Examples of non-interactive Xancil usage
========================================

To read in a previously saved job file and create the UM ancillary files defined by it enter this command line ::

   xancil -j example.job -x

As there are a lot of variables defined in a job file the best approach to scripting Xancil is to create an initial job file which has most of the setup you need and then only change the variables which are different in the script file. For example to create multiple ozone ancillary files from different netCDF input files, assuming everything else needed has been setup using Xancil and saved to a job file called ozone.job, use this script ::


   #!/bin/sh
   
   # Create xancil script file (Needs to be written in tcl)
   
   cat << \EOF > ozone.tcl
   
   # Load in initial job file
   
   source "ozone.job"
   
   set n 12
   
   # Create n ozone ancillary files
   
   set i 1
   
   while {$i <= $n} {
   
      # Overwrite ozone input and output file names
   
      set ozone(file_in) ozone_$i.nc
      set ozone(file_out) ozone_$i
   
      # Create namelist file from Tcl variables
   
      create_namelist ozone.namelist
   
      # Run executable to create ozone ancillary file
   
      run_exec
   
      incr i
   }
   EOF
   
   # Run xancil with the above script file
   
   xancil -sc ozone.tcl

Run this script and Xancil will create 12 ozone ancillary files from 12 netCDF files.

