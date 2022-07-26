.. _introduction:

Introduction
============

Xancil is a X-windows based application for creating Unified Model ancillary files from netCDF input files. The current version supports the creation of the following atmosphere ancillary files

* Ozone
* Soil Moisture and Snow Depth
* Deep Soil Temperatures
* Soil Parameters
* Vegetation Parameters
* Vegetation Fractions
* Vegetation Functional Types
* Disturbed Vegetation Fraction
* Sea Surface Temperatures
* Sea Ice
* Orography
* Land/Sea Mask
* Land Fraction
* Multi-level User fields
* Single-level User fields

along with these ocean ancillary files

* Reference SST, SSS, Air-Temp & Ice-Depth
* Flux Correction Fields
* Multi-level User fields
* Single-level User fields

and finally *Generalised Ancillary Files*  can be used for files which don't fit into the above categories.

Ancillary files can be created for use in both old and new dynamics versions of the UM, and can be in 64 bit IEEE format, including the option of 32 bit data packing, or 32 bit IEEE format. The files can be written in either big or little endian format. Well formed IO (WFIO) ancillary files can be created with a user specified sector size. See the :ref:`config` section for further details.

Xancil will use the input netCDF grid information as the output grid for the ancillary files, so any data interpolation should be done before using Xancil. It doesn't matter whether the input latitude coordinate goes from north to south or south to north, Xancil will ensure the ancillary files use the correct orientation for the specified version of the UM. Similarly longitude values of global grids will be adjusted to the (0,360) degree range expected by the UM. So for example if the input netCDF longitude coordinate is (-180,180) degrees, it does not have to be adjusted for use with Xancil. Ocean ancillary files have two extra wrap-around points in the longitude direction, if the input netCDF file doesn't include these points they will be added by Xancil. Conversely if the input netCDF file includes wrap-around points then Xancil will remove them when creating atmosphere ancillary files. Xancil will create ancillary files on a limited area rotated pole grid, if the input netCDF file includes attributes to define the rotated pole. There are two methods of defining rotated poles which Xancil recognises, the first is to use a two-element floating point attribute ``north_pole`` which specifies the (longitude,latitude) coordinates of the rotated north pole. This attribute is created by Xconv when creating rotated pole netCDF files. The second method is to use the `netCDF CF Metadata <http://cfconventions.org/>`_ convention, where the variables on a rotated grid define an attribute ``grid_mapping``, which specifies the name of another variable which supplies the coordinates of the rotated north pole. See the `CF standard documentation <http://cfconventions.org/Data/cf-conventions/cf-conventions-1.6/build/cf-conventions.html#grid-mappings-and-projections>`_ for further details.

The current state of any information entered into the Xancil panels can be saved as a job file using one of the *Save Job*  or *Save Job As*  buttons and reloaded at a later date using the *Load Job*  button. The job file consists of a list of `Tcl <http://www.tcl.tk/>`_ variables each of which corresponds to an input in a Xancil panel. The *Save Namelist*  or *Save Namelist As*  buttons convert these Tcl variables into a Fortran namelist file and this is used as input to an executable file, which creates the UM ancillary files. By default this executable is called mkancil and is located in the same directory as the xancil executable. The default name for the namelist file is xancil.namelist but this can be changed by using the *Save Namelist As*  button. The *Create Anc. files*  button will create the namelist file and automatically run mkancil to create the UM ancillary files. The *Quit*  button will quit Xancil, any input data will be lost unless a job file has been saved.

Xancil can be given the following command line arguments: ::

   -execute             : Create namelist and run ancillary executable
   -x                   : As -execute
   -execname execfile   : Specify pathname of ancillary executable
                          (default /work/n02/n02/hum/bin/mkancil0.50)
   -xn execfile         : As -execname
   -jobfile jobfile     : Load jobfile into xancil
   -j jobfile           : As -jobfile
   -namelist namelist   : Create namelist file called namelist
                          (default xancil.namelist)
   -nl namelist         : As -namelist
   -namelisttype nltype : Specify namelist type, either old or f90
                          (default f90)
   -script script       : Use xancil to run tcl script
   -sc script           : As -script
   -usage               : Print this message

Examples of command line usage are, run Xancil with the specified job file pre-loaded ::

   xancil -j xancil_example.job

A previously saved job file can be loaded into Xancil, the namelist file created and the mkancil executable run to create the UM ancillary files without using the X-windows interface ::

   xancil -j xancil_example.job -x

Alternatively the mkancil executable can be run directly with the saved namelist file as input ::

   mkancil < xancil.namelist

More elaborate scripting is also possible see :ref:`examples`.

