[![PyPI](https://img.shields.io/pypi/v/DoubleRatchet.svg)](https://pypi.org/project/DoubleRatchet/)
[![PyPI - Python Version](https://img.shields.io/pypi/pyversions/DoubleRatchet.svg)](https://pypi.org/project/DoubleRatchet/)
[![Build Status](https://travis-ci.org/Syndace/python-doubleratchet.svg?branch=stable)](https://travis-ci.org/Syndace/python-doubleratchet)
[![Documentation Status](https://readthedocs.org/projects/python-doubleratchet/badge/?version=latest)](https://python-doubleratchet.readthedocs.io/en/latest/?badge=latest)

# python-doubleratchet #

A Python implementation of the [Double Ratchet algorithm](https://signal.org/docs/specifications/doubleratchet/).

## Installation ##

Install the latest release using pip (`pip install DoubleRatchet`) or manually from source by running `pip install .` (preferred) or `python setup.py install` in the cloned repository.

## Differences to the Specification ##

This library implements the core of the Double Ratchet specification and includes a few of the recommended algorithms. This library does currently _not_ offer sophisticated decision mechanisms for the deletion of skipped message keys. Skipped message keys are only deleted when the maximum amount is reached and old keys are deleted from the storage in FIFO order. There is no time-based or event-based deletion.

## Testing, Type Checks and Linting ##

python-doubleratchet uses [pytest](https://docs.pytest.org/en/latest/) as its testing framework, [mypy](http://mypy-lang.org/) for static type checks and both [pylint](https://pylint.pycqa.org/en/latest/) and [Flake8](https://flake8.pycqa.org/en/latest/) for linting. All tests/checks can be run locally with the following commands:

```sh
$ pip install --upgrade pytest pytest-asyncio mypy pylint flake8
$ mypy --strict doubleratchet/ setup.py examples/ tests/
$ pylint doubleratchet/ setup.py examples/ tests/
$ flake8 doubleratchet/ setup.py examples/ tests/
$ pytest
```

## Documentation ##

View the documentation on [readthedocs.io](https://python-doubleratchet.readthedocs.io/) or build it locally, which requires the Python packages listed in `docs/requirements.txt`. With all dependencies installed, run `make html` in the `docs/` directory. You can find the generated documentation in `docs/_build/html/`.

## Travis CI ##

The project used to be built using Travis CI, which was amazing. Sadly, Travis fully closed their open-source support. I have yet to migrate somewhere else, until then the project will not be automatically tested.
