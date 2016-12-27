
Installing ``pip`` for ``pypy`` in a Development Environment
============================================================

These instructions assume the use of a conda/miniconda environment
but a venv/virtualenv envirment should work as well (adjust
directory references as appropriate).


Instructions
------------

Activate the Python environment::

    source activate <YOUR-ENVIRONMENT-NAME>


Make sure that your site-packages directory exists::

    mkdir ~/miniconda3/envs/<YOUR-ENVIRONMENT-NAME>/site-packages/


Install ``setuptools`` (a requirement for ``pip``)::

    wget https://pypi.python.org/packages/b0/04/d7aac18d0d8b1b9bd9b88af02af8090e72653753bced3226f9903cabb991/setuptools-32.3.0.zip
    unzip setuptools-32.3.0.zip
    cd setuptools-32.3.0
    pypy setup.py install
    cd ..


Install ``pip``, itself::

    wget https://pypi.python.org/packages/11/b6/abcb525026a4be042b486df43905d6893fb04f05aac21c32c638e939e447/pip-9.0.1.tar.gz
    tar -vzxf pip-9.0.1.tar.gz
    cd pip-9.0.1
    pypy setup.py install
    cd ..


Using ``pip``
-------------

To use pip, use the ``-m`` option::

    source activate <YOUR-ENVIRONMENT-NAME>
    pypy -m pip install <PACKAGE-NAME>


Installation Log
-----------------

These instructions have been reported to work for the following instances:

==========  ===========================  ==================
Date        Platform                     Python
==========  ===========================  ==================
2016-12-27  conda 4.1.3 on Ubuntu 16.10  pypy 5.3.1
----------  ---------------------------  ------------------
2016-12-27  conda 4.1.3 on Ubuntu 16.10  pypy3 5.2.0-alpha0
==========  ===========================  ==================
