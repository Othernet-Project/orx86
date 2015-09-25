This tarball contains files necessary to run an ORx receiver on Intel computers
running a 64-bit GNU/Linux distribution.

Prerequisites
=============

Only GNU/Linux operating systems are supported, and only x86_64 platform
supports ONDD. Installation will fail if you run the makefile on an unsupported
platform. 

Python 2.7.x must be installed in order for the install to succeed. You will
get a warning about missing Python runtime during configuration.

You will also need GNU make, which is usually available as part of
build-essential, base-devel, and similar packages.

Tuner does not need to be plugged in during installation but you must have it
plugged in before you start the services.

You will need a *working* DVB-S/S2 tuner. You can check if your device works by
plugging it in and checking whether `/dev/dvb/adapter0/frontend0` exists in 
your filesystem. You may need do find, download, and install firmware files for
your tuner or upgrade your kernel to a more recent version (e.g., 4.1 or 4.2
for HDStar).

Installing
==========

During installation, the following will be installed on your system:

- ONDD binary for your platform
- Librarian
- Librarian configuration file
- Outernet content certificate
- ONDD and Librarian services (init/upstart/systemd scripts)

The services are called `ondd` and `librarian` and you will be able to start
them with your choice of daemon management tools after install is complete.
Note that nothing is done to permanently enable these services. They are simply
installed.

The simplest installation can be done with the following two commands:

    $ ./config
    $ sudo make

Alternatively, you may choose to install only ONDD or only Librarian:

    $ ./config
    $ sudo make ondd

    # or 

    $ sudo make librarian

Uninstalling
============

To uninstall the software:

    $ sudo make uninstall

To uninstall the software and remove any downloaded data:

    $ sudo make scrub

Note: Above commands will fail if you are running them from a freshly unpacked
set of files. You will need to run the `config` script before performing the
uninstall.

Customizing
===========

Customizing is currently undocumented and unsupported. Edit the appropriate
files (`config` script and `Makefile.in` template) to get desired results.

Support
=======

This package is not officially supported, but staff will try to answer your
questions in the forums:

    https://discuss.outernet.is/

Licenses
========

Code in this tarball, as well as most of the software that is installed during
installation are released under GNU GPL v3 license (see COPYING). Code
generated during installation is based on the code from the tarball, and
therefore also covered by the same license. ONDD binary is licensed under a
separate proprietary license (see ONDD-LICENSE). 

By installing and using the software, you agree to the terms of these licenses.

Disclaimer
==========

THIS SOFTAWARE WITH ACCOMPANYING DOCUMENTATION IS EXPERIMENTAL. IT MAY DAMAGE
YOUR SYSTEM AND/OR CAUSE YOU TO LOOSE DATA, TIME, MONEY, AND/OR HAIR. YOU WILL
USE THE SOFTWARE AND DOCUMENTATION AT YOUR OWN RISK. OUTERNET INC AND ANY THIRD
PARTIES THAT PARTICIPATED IN CREATION OF THE SOFTWARE AND ITS DOCUMENTATION
WILL NOT BE LIABLE FOR ANY DAMAGES.
