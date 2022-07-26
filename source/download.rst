.. _download:

Download Xancil
===============

.. _version_0.50:

Updated Version 0.50 (February 19 2010)
---------------------------------------

* Date/times in PP headers for vegetation functional types ancillary file were incorrect.

Download a gzipped tarball of the Mkancil source code

* :download:`Mkancil source <download/vn0.50/mkancil0.50_source.tar.gz>`

Download gzipped tarballs of Xancil/Mkancil executables, for various platforms

* :download:`Linux x86 <download/vn0.50/xancil0.50_linux_x86.tar.gz>`
* :download:`Linux x86_64 <download/vn0.50/xancil0.50_linux_x86_64.tar.gz>`
* :download:`Solaris x86 <download/vn0.50/xancil0.50_solaris_x86.tar.gz>`
* :download:`Solaris Sparc <download/vn0.50/xancil0.50_solaris_sparc.tar.gz>`
* :download:`AIX Powerpc <download/vn0.50/xancil0.50_ibm_aix_powerpc.tar.gz>`

.. _version_0.51:

Version 0.51 (July 01 2011)
---------------------------

* General bug fixes
* Add support to read netCDF4 input files
* Add slab model option to generalised ancillary file creation section

.. _version_0.52:

Version 0.52 (October 13 2011)
------------------------------

* Add orographic gradient x/y components to orography section

.. _version_0.53:

Version 0.53 (August 23 2012)
-----------------------------

* Add option to select horizontal grid type in generalised ancillary file creation section to enable correct creation of ancillary files on u,v grid
* Add support for variable resolution grids
* Add unfiltered orography to orography section

.. _version_0.54:

Version 0.54 (November 28 2012)
-------------------------------

* Fixed problem with reading grid dimensions from fields which don't exist as they aren't being output
* Fixed problem with reading seconds expressed as a real number in the units attribute

.. _version_0.55:

Version 0.55 (March 05 2015)
----------------------------

* Updated CF standard_names to include all names used by CF-python
* Included later UM versions (up-to vn9.2) of STASHmaster information
* Updated font handling to work better with tcl/tk versions greater than 8.4
* Add option to create calendar independent ancillary files

Download a gzipped tarball of the Mkancil source code

* :download:`Mkancil source <download/vn0.55/mkancil0.55_source.tar.gz>`

Download gzipped tarballs (Linux) or a dmg file (OS X) of Xancil/Mkancil executables

* :download:`Linux x86_64 <download/vn0.55/xancil0.55_linux_x86_64.tar.gz>`
* :download:`OS X x86 <download/vn0.55/xancil0.55_osx_x86.dmg>`
* :download:`OS X x86_64 <download/vn0.55/xancil0.55_osx_x86_64.dmg>`

.. _version_0.56:

Version 0.56 (November 15 2016)
-------------------------------

* General bug fixes
* Included later UM versions (up-to vn10.6) of STASHmaster information
* Updates to allow multi-level ancillaries to be created for ENDGame configurations

Download a gzipped tarball of the Mkancil source code

* :download:`Mkancil source <download/vn0.56/mkancil0.56_source.tar.gz>`

Download gzipped tarballs (Linux) or a dmg file (OS X) of Xancil/Mkancil executables

* :download:`Linux x86 <download/vn0.56/xancil0.56_linux_x86.tar.gz>`
* :download:`Linux x86_64 <download/vn0.56/xancil0.56_linux_x86_64.tar.gz>`
* :download:`OS X x86 <download/vn0.56/xancil0.56_osx_x86.dmg>`
* :download:`OS X x86_64 <download/vn0.56/xancil0.56_osx_x86_64.dmg>`

.. _version_0.57:

Version 0.57 (February 01 2017)
-------------------------------

* Fixed bug writing user ancillary files
* Changes to allow creation of ancillary files > 16 GBytes

Download a gzipped tarball of the Mkancil source code

* :download:`Mkancil source <download/vn0.57/mkancil0.57_source.tar.gz>`

Download gzipped tarballs of Xancil/Mkancil executables

* :download:`Linux x86 <download/vn0.57/xancil0.57_linux_x86.tar.gz>`
* :download:`Linux x86_64 <download/vn0.57/xancil0.57_linux_x86_64.tar.gz>`

.. _version_0.58:

Version 0.58 (May 13 2020)
-------------------------------

* General bug fixes
* Included later UM versions (up-to vn11.6) of STASHmaster information
* Improve support for ENDGame grids
* Improve handling of multilevel fields
* Add ability to specify pseudo levels (e.g. surfaces types)
* Improve metadata auto completion in generalised ancillary file panel

Download a gzipped tarball of the Mkancil source code

* :download:`Mkancil source <download/vn0.58/mkancil0.58_source.tar.gz>`

Download gzipped tarballs of Xancil/Mkancil executables

* :download:`Linux x86 <download/vn0.58/xancil0.58_linux_x86.tar.gz>`
* :download:`Linux x86_64 <download/vn0.58/xancil0.58_linux_x86_64.tar.gz>`

To compile Mkancil read the README file contained in the tar file. If you modify Mkancil then Xancil options ``-execname`` or ``-xn`` need to be used to specify the new executable pathname. By default Xancil expects to find Mkancil in the same directory as itself.
