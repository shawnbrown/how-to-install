
Install unittest2 for Python 2.6 on Fedora 30
---------------------------------------------

The most recent versions of ``unittest2`` cannot be installed
without errors Python 2.6. The following instructions install
version 0.2.0::

    # wget https://files.pythonhosted.org/packages/99/a0/41ec4a61afb168cf2d4e2e708f4f070c1cff032a4d288a0985228649fc13/unittest2-0.2.0.tar.gz
    # tar -vzxf unittest2-0.2.0.tar.gz
    # cd unittest2-0.2.0
    # python2.6 setup.py install
    # cd ..
    # rm -f ./unittest2-0.2.0.tar.gz
    # rm -rf ./unittest2-0.2.0
    # exit
    $ python2.6
    >>> import unittest2
    >>> unittest2.__version__
    '0.2.0'


Installation Log
----------------

These instructions have been reported to work for the following instances:

==========  ===========================  ==================
Date        Platform                     Python
==========  ===========================  ==================
2019-08-03  Fedora 30 (Workstation)      Python 2.6.9
==========  ===========================  ==================

