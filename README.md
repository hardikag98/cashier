Cashier
-------
Caching for python functions

A decorator to cache python functions. Extremely handy when you are dealing with I/O heavy operations which seldom changes or CPU intensive functions as well.

Cache function results into a SQLite locally. Extremely handy when you are dealing with I/O heavy operations
which seldom changes or CPU intensive functions as well.


Installation
------------

```pip install cashier```


Usage
-----

from cashier import cache


@cache
def complex_function(a,b,c,d):
    return complex_calculation(a,b,c,d)


Advanced Usage
---------

:param cache_file: sqlite3 file name to which cached data should be written into
    defaults to .cache
:param cache_time: how long should the data be cached
    defaults to 1 day
:param cache_length: how many different arguments and corresponding data should be cached
    defaults to 10000
:param retry_if_blank: If True, will retry for the data if blank data is cached
:return:

Performance Benchmark
---------------------

No Cache Run: 21.309067 seconds

First Caching Run: 20.555911 seconds

Cached Run: 0.519505 seconds (4100 x faster)