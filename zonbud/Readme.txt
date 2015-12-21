                    Zonebudget (ZONBUD) - Version: 3.01
              Program for computing subregional water budgets
                    for MODFLOW ground-water flow models

NOTE: Any use of trade, product or firm names is for descriptive purposes 
      only and does not imply endorsement by the U.S. Government.

Instructions for installing, executing, and testing ZONBUD are 
provided below.

This version of Zonebudget is packaged for use on personal computers
using a Microsoft Windows operating system. For invoking Zonebudget,
the acronym ZONBUD is used.


                            TABLE OF CONTENTS

                         A. DISTRIBUTION FILE
                         B. EXTRACTING FILES
                         C. COMPILING
                         D. INSTALLING
                         E. RUNNING THE SOFTWARE
                         F. TESTING


A. DISTRIBUTION FILE

The following self-extracting distribution file, containing the software,
test data sets, and information files, is currently available for
Microsoft Windows computer systems:

         zonbud3_01.exe


B. EXTRACTING FILES

Extract the files by executing file:

        zonbud3_01.exe

When the extraction progrm runs, the default extraction directory is
C:\WRDAPP
 

The following directory structure will be created in the extraction
directory:

      ZONBUD.3_01      ; copy of this readme file
        |-----bin       ; executable runfile
        |-----doc       ; documentation files
        |-----src       ; source code
        |-----data      ; test dataset


File ZONBUD.3_01\doc\zonbud3.pdf describes the changes to the code,
since the original version (1.0). Also included in directory
ZONBUD.3_01\doc is a Portable Document Format (PDF) version of the
ZONEBUDGET documentatoin (ofr90392.pdf).

It is recommended that no user files are kept in the ZONBUD.3_01
directory structure.


C. COMPILING

An executable version of the code for personal computers is provided in
the bin directory; however, the source code is also provided in the src
directory so that users can generate the executable themselves. No
support can be provided for users generating their own versions of the
software.  In general, the requirements are a Fortran compiler and
knowledge about using the compiler.


D: INSTALLING

To make the ZONBUD program accessible from any directory, the directory
containing the executable should be included in the PATH environment
variable.


E. RUNNING THE SOFTWARE

ZONBUD has been compiled using the Intel compiler version 11.0.

After ZONBUD is properly installed in a directory that is included in
your PATH, the program is initiated using the command:  ZONBUD.  The
details of program operation are provided in file zonbud3.pdf in the
doc directory.

The runfile for version 3.01 of ZONBUD for use on personal computers has
been created using the compiler options that will allow ZONBUD to
read the unstructured unformatted budget files created by current
versions of MODFLOW-2000 and MODFLOW-2005 distributed on USGS web
pages. Other compilers could be used to compile MODFLOW provided that
they cause unformatted files to be written in the same unstructured
manner.  However, if compiler options are used that cause MODFLOW to
generate structured binary files, then it is necessary that ZONBUD be
compiled with the same compiler used to compile MODFLOW.

Starting with MODFLOW-2000 version 1.2, the USGS-distributed MODFLOW
runfile for personal computers is compiled using the above-mentioned
options for writing unstructured unformatted files.  If you are using
an earlier version of a MODFLOW runfile produced by the USGS, then the
provided ZONBUD runfile will not be able to read the unformatted budget
files.


F. TESTING

A test data set is provided to verify that the program is correctly
installed and running on the system.  The directory ZONBUD.3_01\data
contains the input data and expected results for the test.

The test is the example problem in the original Zonebudget
documentation report, OFR 90-392.

The MODFLOW input data files are
               Name File to designate files       zbtest.nam
               BAS6 Package                       zbtest.ba6
               BCF6 Package                       zbtest.bc6
               Discretization file                zbtest.dis
               SIP5 Package                       zbtest.sip
               Output Control                     zbtest.oc
               RCH5 Package                       zbtest.rch
               WEL5 Package                       zbtest.wel

The MODFLOW output files are
               cell-by-cell flow data             zbtest.bud
               Listing file                       zbtest.lst

Run Zonebudget and enter the following responses to the prompts:

The name of the LISTING File for results:                   zbtest.zblst
The name of the file containing CELL-BY-CELL BUDGET TERMS:  zbtest.bud
TITLE:                                                      Test
The name of the ZONE INPUT FILE:                            zbtest.zon
Option for specifying when budgets are calculated:          A


When done, look in file zbtest.zblst for the results.

The cell-by-cell data file (zbtest.bud) was generated using MODFLOW-2005
version 1.5 as distributed on the USGS web page.  zbtest.bud is an
unstructured unformatted file that is compiler and platform dependent;
However, if you compile ZONBUD using compiler options that create
structured unformatted files, you will need to recreate the budget file
using a version of MODFLOW compiled with the same compiler. 
