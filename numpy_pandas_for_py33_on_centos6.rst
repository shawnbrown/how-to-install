
.. warning::

    These instructions were used for for ``numpy`` 1.8.1 (released
    2014-03-25) and ``pandas`` 0.13.1 (released 2014-04-03).


NumPy and Pandas for Python 3.3 on CentOS 6
===========================================

The following commands use Python 3.3 via the CentOS/RHEL Software
Collections (the *"scl enable..."* line)::

    $ sudo su -
    $ yum install gcc-gfortran
    $ yum install libgfortran
    $ yum install lapack
    $ yum install gcc-c++
    $ scl enable python33 bash
    $ pip install numpy
    $ pip install pandas
    $ exit
    $ exit


Installation Log
-----------------

These instructions have been reported to work for the following instances:

==========  ===========================  ==================
Date        Platform                     Python
==========  ===========================  ==================
2014-04-03  CentOS 6                     Python 3.3
==========  ===========================  ==================
