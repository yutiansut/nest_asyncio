|Build| |Status| |PyPiVersion| |License|

Introduction
------------

By design asyncio `does not allow <https://bugs.python.org/issue22239>`_
its event loop to be nested. This presents a practical problem:
When in an environment where the event loop is
already running it's impossible to run tasks and wait
for the result. Trying to do so will give the error
"``RuntimeError: This event loop is already running``".

The issue pops up in various environments, such as web servers, GUI applications
and in Jupyter notebooks.

This module patches asyncio to allow nested use of ``asyncio.run`` and
``loop.run_until_complete``.

Installation
------------

.. code-block::

    pip3 install nest_asyncio

Python 3.5 or higher is required.

Usage
-----

.. code-block:: python

    import nest_asyncio
    nest_asyncio.apply()

.. |Build| image:: https://travis-ci.org/erdewit/nest_asyncio.svg?branch=master
   :alt: Build
   :target: https://travis-ci.org/erdewit/nest_asyncio

.. |PyPiVersion| image:: https://img.shields.io/pypi/v/nest_asyncio.svg
   :alt: PyPi
   :target: https://pypi.python.org/pypi/nest_asyncio

.. |Status| image:: https://img.shields.io/badge/status-beta-green.svg
   :alt:

.. |License| image:: https://img.shields.io/badge/license-BSD-blue.svg
   :alt:

