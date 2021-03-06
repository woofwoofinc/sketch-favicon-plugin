.. _documentation:

Documentation
=============
The project documentation under ``src`` can be compiled using Sphinx_. Output
is placed in ``src/_build/html``.

.. _Sphinx: http://www.sphinx-doc.org

::

    cd src
    make clean html

The development container provides an installation of Python and Sphinx which
can be used to build this documentation also.

Build the container as described in :ref:`dev`. Then change to the ``src``
directory that you want to compile and start the container with this directory
mounted at ``/sketch-favicon``.

::

    sudo rkt run \
        --interactive \
        --volume sketch-favicon,kind=host,source=$(pwd) \
        dev-sketch-favicon \
        --mount volume=sketch-favicon,target=/sketch-favicon

Inside the container, change directory to ``/sketch-favicon`` and run the build
command.

::

    cd /sketch-favicon
    make clean html

The compiled document is written to the shared location and is available on the
host machine under ``src/_build/html``.
