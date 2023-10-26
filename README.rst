Introduction
============


.. image:: https://readthedocs.org/projects/adafruit-circuitpython-cst8xx/badge/?version=latest
    :target: https://docs.circuitpython.org/projects/cst8xx/en/latest/
    :alt: Documentation Status


.. image:: https://raw.githubusercontent.com/adafruit/Adafruit_CircuitPython_Bundle/main/badges/adafruit_discord.svg
    :target: https://adafru.it/discord
    :alt: Discord


.. image:: https://github.com/adafruit/Adafruit_CircuitPython_CST8XX/workflows/Build%20CI/badge.svg
    :target: https://github.com/adafruit/Adafruit_CircuitPython_CST8XX/actions
    :alt: Build Status


.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
    :target: https://github.com/psf/black
    :alt: Code Style: Black

CST8xx capacitive touch driver for CircuitPython


Dependencies
=============
This driver depends on:

* `Adafruit CircuitPython <https://github.com/adafruit/circuitpython>`_
* `Bus Device <https://github.com/adafruit/Adafruit_CircuitPython_BusDevice>`_

Please ensure all dependencies are available on the CircuitPython filesystem.
This is easily achieved by downloading
`the Adafruit library and driver bundle <https://circuitpython.org/libraries>`_
or individual libraries can be installed using
`circup <https://github.com/adafruit/circup>`_.

* Round RGB 666 TTL TFT Display - 2.1" 480x480 - Capacitive Touch - TL021WVC02CT-B1323

`Purchase one from the Adafruit shop <http://www.adafruit.com/product/5792>`_

Installing from PyPI
=====================
On supported GNU/Linux systems like the Raspberry Pi, you can install the driver locally `from
PyPI <https://pypi.org/project/adafruit-circuitpython-cst8xx/>`_.
To install for current user:

.. code-block:: shell

    pip3 install adafruit-circuitpython-cst8xx

To install system-wide (this may be required in some cases):

.. code-block:: shell

    sudo pip3 install adafruit-circuitpython-cst8xx

To install in a virtual environment in your current project:

.. code-block:: shell

    mkdir project-name && cd project-name
    python3 -m venv .venv
    source .env/bin/activate
    pip3 install adafruit-circuitpython-cst8xx

Installing to a Connected CircuitPython Device with Circup
==========================================================

Make sure that you have ``circup`` installed in your Python environment.
Install it with the following command if necessary:

.. code-block:: shell

    pip3 install circup

With ``circup`` installed and your CircuitPython device connected use the
following command to install:

.. code-block:: shell

    circup install adafruit_cst8xx

Or the following command to update an existing version:

.. code-block:: shell

    circup update

Usage Example
=============

.. code-block:: python

    import board
    import adafruit_cst8xx

    ctp = adafruit_cst8xx.Adafruit_CST8XX(board.I2C())

    events = adafruit_cst8xx.EVENTS
    while True:
        if ctp.touched:
            for touch_id, touch in enumerate(ctp.touches):
                x = touch["x"]
                y = touch["y"]
                event = events[touch["event_id"]]
                print(f"touch_id: {touch_id}, x: {x}, y: {y}, event: {event}")

Documentation
=============
API documentation for this library can be found on `Read the Docs <https://docs.circuitpython.org/projects/cst8xx/en/latest/>`_.

For information on building library documentation, please check out
`this guide <https://learn.adafruit.com/creating-and-sharing-a-circuitpython-library/sharing-our-docs-on-readthedocs#sphinx-5-1>`_.

Contributing
============

Contributions are welcome! Please read our `Code of Conduct
<https://github.com/adafruit/Adafruit_CircuitPython_CST8XX/blob/HEAD/CODE_OF_CONDUCT.md>`_
before contributing to help this project stay welcoming.
