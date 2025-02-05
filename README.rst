Introduction
============

.. image:: https://readthedocs.org/projects/adafruit-circuitpython-ble/badge/?version=latest
    :target: https://circuitpython.readthedocs.io/projects/ble/en/latest/
    :alt: Documentation Status

.. image:: https://img.shields.io/discord/327254708534116352.svg
    :target: https://discord.gg/nBQh6qu
    :alt: Discord

.. image:: https://travis-ci.com/adafruit/Adafruit_CircuitPython_ble.svg?branch=master
    :target: https://travis-ci.com/adafruit/Adafruit_CircuitPython_ble
    :alt: Build Status

This module provides higher-level BLE (Bluetooth Low Energy) functionality,
building on the native `_bleio` module.

Dependencies
=============
This driver depends on:

* `Adafruit CircuitPython <https://github.com/adafruit/circuitpython>`_

Please ensure all dependencies are available on the CircuitPython filesystem.
This is easily achieved by downloading
`the Adafruit library and driver bundle <https://github.com/adafruit/Adafruit_CircuitPython_Bundle>`_.

Usage Example
=============

.. code-block:: python

    from adafruit_ble import BLERadio

    radio = BLERadio()
    print("scanning")
    found = set()
    for entry in radio.start_scan(timeout=60, minimum_rssi=-80):
        addr = entry.address
        if addr not in found:
            print(entry)
        found.add(addr)

    print("scan done")


Contributing
============

Contributions are welcome! Please read our `Code of Conduct
<https://github.com/adafruit/Adafruit_CircuitPython_ble/blob/master/CODE_OF_CONDUCT.md>`_
before contributing to help this project stay welcoming.

Documentation
=============

For information on building library documentation, please check out `this guide <https://learn.adafruit.com/creating-and-sharing-a-circuitpython-library/sharing-our-docs-on-readthedocs#sphinx-5-1>`_.
