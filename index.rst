.. maddlib documentation master file, created by
   sphinx-quickstart on Sat Jan 25 12:13:40 2025.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

maddlib documentation
=====================

|Python version|

.. |Python version| image:: https://img.shields.io/badge/python-3.10.4-green.svg
   :target: https://img.shields.io/badge/python-3.10.4-green.svg



maddlib is a Python library for algorithmic fairness assessment and mitigation with the MADD metric. MADD, which stands for *Model Absolute Density Distance*, is a fairness metric based on the distance of the distributions of the probability estimates or confidence scores of machine learning classifiers or regressors (except SVM models).

Source code on `GitHub <https://github.com/melinaverger/maddlib>`_ and `PyPI <https://pypi.org/project/maddlib/>`_. 

Can be used with popular ML libraries such as Pandas and Scikit-learn.

.. note::

   This project is under active development.


Installation
------------

.. code-block:: console

   (.venv) $ pip install maddlib

or

.. code-block:: console
   
   (.venv) $ python3 -m pip install maddlib

If you have an error, please check first that your Python version is greater than 3.10.4.

Upgrade
-------

.. code-block:: console
   
   (.venv) $ pip install --upgrade maddlib

or

.. code-block:: console

   (.venv) $ python3 -m pip install --upgrade pip


.. toctree::
   :maxdepth: 2
   :caption: Contents:

   eval
   optimalBandwidth
   postProcessing
   version