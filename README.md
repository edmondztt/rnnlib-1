RNNLIB is written in C++ by Alex Graves and should compile on any platform. However it is currently only tested for Linux and OSX.

[![Build Status](https://travis-ci.org/xavigonzalvo/rnnlib.svg)](https://travis-ci.org/xavigonzalvo/rnnlib)

Building it requires the following:

* A modern C++ compiler (e.g. gcc 3.0 or higher)
* GNU Libtool
* GNU automake version 1.9 or higher
* the NetCDF scientific data library including binaries (NetCDF from http://www.unidata.ucar.edu/software/netcdf/, and binaries nco from http://nco.sourceforge.net/).
* Boost C++ Libraries version 1.5 or higher (headers only, no compilation needed)

In addition, the following python packages are needed for the auxiliary scripts in the 'utils' directory:

* SciPy
* PyLab
* PIL

And this package is needed to create and manipulate netcdf data files with python, and to run the experiments in the 'examples' directory:

* ScientificPython (NOT Scipy)
http://dirac.cnrs-orleans.fr/plone/software/scientificpython/installation-instructions/
When building, make sure you specify export NETCDF_PREFIX=/opt/local/.

To build RNNLIB, first download the source from here, then enter the root directory and type

    $ ./configure
    $ make

This should create the binary file 'rnnlib' in the 'bin' directory. 
Note that on most linux systems the default installation directory for the Boost headers is '/usr/local/include/boost-VERSION_NUMBER' which is not on the standard include path. 
In this case type

    $ CXXFLAGS=-I/usr/local/include/boost-VERSION_NUMBER/ ./configure
    $ CXXFLAGS="-I/opt/local/include/ -L/opt/local/lib" ./configure
    $ make

If you wish to install the binary type:

    $ make install

By default this will use '/usr' as the installation root (for which you will usually need administrator privileges). 
You can change the install path with the —prefix option of the configure script (use ./configure —help for other options)

It is recommended that you add the directory containing the 'rnnlib' binary to your path,
as otherwise the tools in the 'utilities' directory will not work.

Project files are provided for the following integrated development environments in the 'ide' directory:

* kdevelop (KDE, linux)
* xcode (OSX)
