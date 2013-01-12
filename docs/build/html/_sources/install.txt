.. _install:

Installation
============


Using PIP
---------

The latest stable-ish build::

    pip install pybbm-extensions

Development version::

    pip install git+https://bitbucket.org/zalew/pybbm-extensions


From source
-----------

::

    git clone https://bitbucket.org/zalew/pybbm-extensions
    cd pybbm-extensions
    ./setup.py install
    
    
Settings
---------

.. code-block:: python

    INSTALLED_APPS = (
        ...
        'pybb_extensions.pluggable',
    )

.. code-block:: shell

    ./manage.py syncdb
    

Dependencies
------------

* `Django`_ 
* `PyBBm`_ 

.. _`Django`: https://www.djangoproject.com/
.. _`PyBBm`: http://pypi.python.org/pypi/pybbm


Upgrading
----------

`South
<http://south.readthedocs.org/en/latest/index.html>`_ is used for migrations.

