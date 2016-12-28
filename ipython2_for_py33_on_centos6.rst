
.. warning::

    These instructions are for an older version of IPython (now renamed
    to Jupyter).  It is recommended that users install the new `Jupyter
    Notebook <https://pypi.python.org/pypi/jupyter/>`_ version instead.


IPython 2 on CentOS 6
=====================

The following commands use python33 from the CentOS/RHEL Software
Collections (the *"scl enable..."* line) and includes dependencies for
IPython Notebook::

    $ sudo su -
    $ yum install gcc-c++
    $ scl enable python33 bash
    $ pip install pyzmq
    $ pip install tornado
    $ pip install jinja2
    $ pip install ipython>=2.0.0
    $ exit
    $ exit


Installation Log
----------------

These instructions have been reported to work for the following instances:

==========  ===========================  ==================
Date        Platform                     Python
==========  ===========================  ==================
2014-04-03  CentOS 6                     Python 3.3
==========  ===========================  ==================
