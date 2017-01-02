
.. meta::
    :description: How to install pip on Linux.
    :keywords: how to install pip, from source, linux
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
* For the following commands, replace ``<PYTHON-EXECUTABLE>`` with the
  command for the Python instance you want to use.


1. Install ``setuptools``
=========================

The `setuptools <https://pypi.python.org/pypi/setuptools>`_ package is
a requirement for pip, install it from source with the following
comands:

.. code-block:: bash

    $ wget https://pypi.python.org/packages/b0/04/d7aac18d0d8b1b9bd9b88af02af8090e72653753bced3226f9903cabb991/setuptools-32.3.0.zip
    $ unzip setuptools-32.3.0.zip
    $ cd setuptools-32.3.0
    $ <PYTHON-EXECUTABLE> setup.py install
    $ cd ..


2. Install ``pip`` itself
=========================

Once the requirement is satisfied, install pip from source:

.. code-block:: bash

    $ wget https://pypi.python.org/packages/11/b6/abcb525026a4be042b486df43905d6893fb04f05aac21c32c638e939e447/pip-9.0.1.tar.gz
    $ tar -vzxf pip-9.0.1.tar.gz
    $ cd pip-9.0.1
    $ <PYTHON-EXECUTABLE> setup.py install
    $ cd ..

If the above commands worked, **you're done!**


Using ``pip``
=============

When using pip, make sure to call the correct version by using the
``-m`` syntax:

.. code-block:: bash

    $ <PYTHON-EXECUTABLE> -m pip install <PACKAGE-NAME>

This format is useful when you have multiple versions of Python
installed or when working with multiple development environments.


Specific Examples
=================

Inside a ``venv`` or ``conda`` Environment
------------------------------------------

When activating a `venv <https://docs.python.org/3/library/venv.html>`_
or `conda <https://pypi.python.org/pypi/conda>`_ environment, the
``python`` command is automatically associated with the appropriate
Python executable so we simply use *"python setup.py ..."* in the
commands below:

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

Once pip is set up, we can install the  `requests
<https://pypi.python.org/pypi/requests>`_ package with the
following commands:

.. code-block:: bash

    $ source activate py36env
    $ python -m pip install requests


For ``pypy3`` in a ``conda`` Environment
----------------------------------------

The additional *"mkdir ..."* command makes sure that the
``/site-packages/`` directory is present (sometimes it can be missing
when PyPy is installed inside a conda environment):

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

Once pip is set up, we can install the ``requests`` package with the
following commands:

.. code-block:: bash

    $ source activate pypy3env
    $ pypy3 -m pip install requests


For Python 2.7 Installed Directly on the System
-----------------------------------------------

To properly install packages for an instance of Python that has been
installed directly on your system (not within a development
environment), you must use an account with administrator permissions
(enabled with *"sudo su -"* below). Additional *"rm ..."* commands are
included to keep the root environment tidy:

.. code-block::

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

Once pip is set up, we can install the ``requests`` package with the
following commands:

.. code-block::

    $ sudo su -
    # python2.7 -m pip install requests
    # exit


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
