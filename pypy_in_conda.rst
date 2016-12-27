
PyPy inside a Conda Environment
===============================

The following instructions describe how to create a conda environment with installed inside. They use Alexey Strokach's `conda packages <https://anaconda.org/ostrokach/>`_.


pypy (Python 2.7 compatible)
----------------------------

Create a new environment with PyPy inside::

    conda create --name pypy -c ostrokach pypy=5.3.1


Confirm installation using ``which``::

    $ source activate pypy
    $ which pypy
    $ source deactivate

The above call to ``which`` should return::

    /home/<USER>/miniconda3/envs/pypy/bin/pypy


pypy3 (Python 3.3 compatible)
-----------------------------

Create a new environment with PyPy3 inside::

    conda create --name pypy3 -c ostrokach pypy3.3=5.2

Confirm installation using ``which``::

    $ source activate pypy3
    $ which pypy3
    $ source deactivate

The above call to ``which`` should return::

    /home/<USER>/miniconda3/envs/pypy3/bin/pypy3


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
