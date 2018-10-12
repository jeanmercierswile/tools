Docker-Nox
==========

|imagelayers| |dockerpulls|

Description
-----------

Provides an (unofficial) docker container for the `nox`_ tool along with all
`currently supported versions of Python`_. To be more specific: this contains
the *latest patch for each non-EOL'ed minor version*.

Note that the `nox`_ tool was formerly known as `nox-automation`_, so older
tags of this image exist which reference `nox-automation`_ releases rather than
`nox`_ releases.

Usage
-----

This image is meant to be used as a development environment or in CI systems.
For example, if you use CircleCI, you might have:

.. code-block:: yaml

    test:
        docker:
            - image: thekevjames/nox:2018.10.9
        steps:
            - checkout
            - run: nox

To run your tests locally, you could do:

.. code-block:: console

    docker run --rm -it -v $(pwd):/src thekevjames/nox:2018.10.9 nox -f src/noxfile.py

Or, to maintain your nox cache between runs:

.. code-block:: console

    docker run --rm -it -v $(pwd):/src thekevjames/nox:2018.10.9 bash
    $ nox -f src/noxfile.py
    # repeat as necessary

For full usage information, see the `nox`_ documentation.

.. _currently supported versions of Python: https://devguide.python.org/#status-of-python-branches
.. _nox-automation: https://pypi.org/project/nox-automation
.. _nox: http://nox.thea.codes/en/stable/
.. |dockerpulls| image:: https://img.shields.io/docker/pulls/thekevjames/nox.svg?style=flat-square
    :alt: Docker Pulls
    :target: https://hub.docker.com/r/thekevjames/nox/
.. |imagelayers| image:: https://img.shields.io/imagelayers/image-size/thekevjames/nox/latest.svg?style=flat-square
    :alt: ImageLayers Size
    :target: https://hub.docker.com/r/thekevjames/nox/