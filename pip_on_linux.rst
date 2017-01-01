
.. meta::
    :description: Instructions for installing pip on Linux.
    :keywords: how to install pip, linux
    :author: Shawn Brown


############################################################
Install ``pip`` on Linux (for a specific instance of Python)
############################################################

These instructions explain how to install `pip
<https://pypi.python.org/pypi/pip>`_ from source on Linux for specific
Python installations.

* Most installations of Python include pip by default.
* But some installs don't include it (virtual environments created with
  ``--no-site-packages``, some PyPy installs, etc.).
* Once installed, pip will only manage packages for the specific
  version of Python it's associated with.


1. Install ``setuptools``
=========================

The ``setuptools`` package is a requirement for ``pip``, install it from
source with the following comands:

.. code-block:: bash

    $ wget https://pypi.python.org/packages/b0/04/d7aac18d0d8b1b9bd9b88af02af8090e72653753bced3226f9903cabb991/setuptools-32.3.0.zip
    $ unzip setuptools-32.3.0.zip
    $ cd setuptools-32.3.0
    $ <PYTHON-EXECUTABLE> setup.py install
    $ cd ..


2. Install ``pip``, itself
==========================

Once the requirement is satisfied, install ``pip`` from source:

.. code-block:: bash

    $ wget https://pypi.python.org/packages/11/b6/abcb525026a4be042b486df43905d6893fb04f05aac21c32c638e939e447/pip-9.0.1.tar.gz
    $ tar -vzxf pip-9.0.1.tar.gz
    $ cd pip-9.0.1
    $ <PYTHON-EXECUTABLE> setup.py install
    $ cd ..

If the above commands worked, **you're done!**


Using ``pip``
=============

To make sure you are using the correct version of pip, use the ``-m`` option as shown here:

.. code-block:: bash

    $ <PYTHON-EXECUTABLE> -m pip install <PACKAGE-NAME>

This format is useful when you have multiple versions of Python
installed or when working with multiple development environments.


Specific Examples
=================

Inside a ``venv`` or ``conda`` Environment
------------------------------------------

Once a ``venv`` or ``conda`` environment has been activated, the
``python`` command is associated with the appropriate Python executable
so we simply use *"python setup.py install"* below:

.. code-block:: bash

    $ source activate py36env

    $ wget https://pypi.python.org/packages/b0/04/d7aac18d0d8b1b9bd9b88af02af8090e72653753bced3226f9903cabb991/setuptools-32.3.0.zip
    $ unzip setuptools-32.3.0.zip
    $ cd setuptools-32.3.0
    $ python setup.py install
    $ cd ..

    $ wget https://pypi.python.org/packages/11/b6/abcb525026a4be042b486df43905d6893fb04f05aac21c32c638e939e447/pip-9.0.1.tar.gz
    $ tar -vzxf pip-9.0.1.tar.gz
    $ cd pip-9.0.1
    $ python setup.py install
    $ cd ..


For ``pypy3`` in a ``conda`` Environment
----------------------------------------

These instructions assume the use of a conda/miniconda environment
but a venv/virtualenv envirment should work as well (adjust
directory references as appropriate).


.. code-block:: bash

    $ source activate pypy3env
    $ mkdir ~/miniconda3/envs/pypy3env/site-packages/

    $ wget https://pypi.python.org/packages/b0/04/d7aac18d0d8b1b9bd9b88af02af8090e72653753bced3226f9903cabb991/setuptools-32.3.0.zip
    $ unzip setuptools-32.3.0.zip
    $ cd setuptools-32.3.0
    $ pypy3 setup.py install
    $ cd ..

    $ wget https://pypi.python.org/packages/11/b6/abcb525026a4be042b486df43905d6893fb04f05aac21c32c638e939e447/pip-9.0.1.tar.gz
    $ tar -vzxf pip-9.0.1.tar.gz
    $ cd pip-9.0.1
    $ pypy3 setup.py install
    $ cd ..


For Python 2.7 Installed Directly on the System
-----------------------------------------------

To properly install packages for an instance of Python that has been
installed directly on your system (not within a development
environment), you must use an account with administrator permissions
(enabled with *"sudo su -"* below):

.. code-block:: bash

    $ sudo su -

    # wget https://pypi.python.org/packages/b0/04/d7aac18d0d8b1b9bd9b88af02af8090e72653753bced3226f9903cabb991/setuptools-32.3.0.zip
    # unzip setuptools-32.3.0.zip
    # cd setuptools-32.3.0
    # python2.7 setup.py install
    # cd ..

    # wget https://pypi.python.org/packages/11/b6/abcb525026a4be042b486df43905d6893fb04f05aac21c32c638e939e447/pip-9.0.1.tar.gz
    # tar -vzxf pip-9.0.1.tar.gz
    # cd pip-9.0.1
    # python2.7 setup.py install
    # cd ..

    # rm ./setuptools-32.3.0.zip
    # rm ./pip-9.0.1.tar.gz
    # rm -r ./setuptools-32.3.0
    # rm -r ./pip-9.0.1
    # exit

The clean-up commands are included to keep the root environment tidy.


Installation Log
-----------------

These instructions have been reported to work for the following instances:

==========  ===========================  ==================
Date        Platform                     Python
==========  ===========================  ==================
2016-12-31  Ubuntu 16.10                 Python 2.7
----------  ---------------------------  ------------------
2016-12-27  conda 4.1.3 on Ubuntu 16.10  pypy 5.3.1
----------  ---------------------------  ------------------
2016-12-27  conda 4.1.3 on Ubuntu 16.10  pypy3 5.2.0-alpha0
==========  ===========================  ==================
