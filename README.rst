Bow -  ̶B̶e̶t̶t̶e̶r̶ Faster dates & times for Python
=======================================

.. image:: https://travis-ci.org/crsmithdev/arrow.svg
   :alt: build status
   :target: https://travis-ci.org/crsmithdev/arrow

.. image:: https://codecov.io/github/crsmithdev/arrow/coverage.svg?branch=master
   :target: https://codecov.io/github/crsmithdev/arrow
   :alt: Codecov

.. image:: https://img.shields.io/pypi/v/arrow.svg
   :target: https://pypi.python.org/pypi/arrow
   :alt: downloads
        
Documentation: `arrow.readthedocs.org <http://arrow.readthedocs.org/en/latest/>`_
---------------------------------------------------------------------------------

What?
-----

Bow is my personal fork of [Arrow](https://github.com/crsmithdev/arrow) for increased performance. So far I've focused on the DateTimeParser and porting it over to Cython.


Why?
----
When creating data pipelines, parsing dates is one of the slowest operations. The default cpython implementation of `strptime` is very slow. At least according to annecdotal experience and other experiments such as [this](https://aboutsimon.com/blog/2016/08/04/datetime-vs-Arrow-vs-Pendulum-vs-Delorean-vs-udatetime.html). For an ingestion job that needs to say parse 1 million dates, around 5 minutes will be spent parsing dates (depending on machine). These optimizations are yielding anywhere from 30%-1000% performance increases depending on the use case. 

