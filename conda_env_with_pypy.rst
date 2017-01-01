
.. meta::
    :description: How to install PyPy in a conda environment.
    :keywords: how to install pypy in conda, linux
    :author: Shawn Brown


###################################
Create a Conda Environment for PyPy
###################################

The following notes describe how to create a `conda
<https://pypi.python.org/pypi/conda>`_ environment with PyPy installed
inside. These instructions use Alexey Strokach's `conda packages
<https://anaconda.org/ostrokach/>`_ and only work for Linux.


PyPy3
=====

Create a new environment with with PyPy3 (Python3.3 compatible) inside:

.. code-block:: bash

    $ conda create --name pypy3 -c ostrokach pypy3.3=5.2

Activate the environment and start the interactive prompt:

.. code-block:: bash

    $ source activate pypy3
    $ pypy3

If the PyPy3 starts, **it's working!** Quit the interactive prompt:

.. code-block:: bash

    >>>> exit()


PyPy
====

Create a new environment with PyPy (Python2.7 compatible) inside:

.. code-block:: bash

    $ conda create --name pypy -c ostrokach pypy=5.3.1


Activate the environment and start the interactive prompt:

.. code-block:: bash

    $ source activate pypy
    $ pypy

If PyPy starts, **it's working!** Quit the interactive prompt:

.. code-block:: bash

    >>>> exit()


Installation Log
-----------------

These instructions have been reported to work for the following instances:

==========  ===========================  ==================
Date        Platform                     Python
==========  ===========================  ==================
2016-12-21  conda 4.1.3 on Ubuntu 16.10  pypy 5.3.1
----------  ---------------------------  ------------------
2016-12-21  conda 4.1.3 on Ubuntu 16.10  pypy3 5.2.0-alpha0
==========  ===========================  ==================
