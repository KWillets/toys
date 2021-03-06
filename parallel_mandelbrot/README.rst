================================================================================
                    Parallel Mandelbrot set generator
================================================================================

Multithread generator of `Mandelbrot set`__ images.
On system with 2 CPUs speedup is around 1.95 --- 1.99.

__ http://en.wikipedia.org/wiki/Mandelbrot_set


Performance on a machine with 8 CPUs
------------------------------------------------------------------------

Image size: 4094 x 4096

Speedup on Core(TM) i7-3612QM CPU @ 2.10GHz

+---------+----------+-------------+
| threads | time [s] | speedup [%] |
+=========+==========+=============+
| 1       | 5.876    | 100         |
+---------+----------+-------------+
| 2       | 3.028    | 194         |
+---------+----------+-------------+
| 3       | 2.163    | 272         |
+---------+----------+-------------+
| 4       | 1.617    | 363         |
+---------+----------+-------------+
| 5       | 1.369    | 429         |
+---------+----------+-------------+
| 6       | 1.215    | 484         |
+---------+----------+-------------+
| 7       | 1.052    | 559         |
+---------+----------+-------------+
| 8       | 0.934    | 629         |
+---------+----------+-------------+
| 9       | 0.934    | 629         |
+---------+----------+-------------+
| 10      | 0.935    | 628         |
+---------+----------+-------------+
| 11      | 0.940    | 625         |
+---------+----------+-------------+
| 12      | 0.945    | 622         |
+---------+----------+-------------+
| 13      | 0.932    | 630         |
+---------+----------+-------------+
| 14      | 0.938    | 626         |
+---------+----------+-------------+
| 15      | 0.932    | 630         |
+---------+----------+-------------+
| 16      | 0.941    | 624         |
+---------+----------+-------------+

.. image:: results.png


Performance on a machine with 32 CPUs
------------------------------------------------------------------------

Image size: 4094 x 4096

CPU: Xeon(R) CPU E7-8837 @ 2.67GHz

+---------+----------+-------------+
| threads | time [s] | speedup     |
+=========+==========+=============+
| 1       | 7.284    |  1.00       |
+---------+----------+-------------+
| 4       | 1.859    |  3.92       |
+---------+----------+-------------+
| 8       | 0.935    |  7.79       |
+---------+----------+-------------+
| 16      | 0.484    | 15.05       |
+---------+----------+-------------+
| 32      | 0.274    | 26.58       |
+---------+----------+-------------+

The program doesn't scale well.


Performance on a machine with 64 CPUs
------------------------------------------------------------------------

Image size: 4094 x 4096

CPU: Xeon(R) CPU E7-8837 v3 @ 2.50GHz

+---------+----------+-------------+-------------+
| threads | time [s] | speedup     | relative    |
+=========+==========+=============+=============+
|    1    |  6.450   |   1.00      | n/a         |
+---------+----------+-------------+-------------+
|    4    |  1.619   |   3.98      |   3.98      |
+---------+----------+-------------+-------------+
|    8    |  0.820   |   7.86      |   1.97      |
+---------+----------+-------------+-------------+
|   16    |  0.438   |  14.73      |   1.87      |
+---------+----------+-------------+-------------+
|   32    |  0.246   |  26.22      |   1.78      |
+---------+----------+-------------+-------------+
|   64    |  0.166   |  38.86      |   1.48      |
+---------+----------+-------------+-------------+
|  128    |  0.103   |  62.62      |   1.61      |
+---------+----------+-------------+-------------+
|  256    |  0.105   |  61.43      |   0.98      |
+---------+----------+-------------+-------------+


Performance on Knights Landing (64 CPUs, 256 threads)
------------------------------------------------------------------------

Image size: 4094 x 4096

+---------+----------+-------------+-------------+
| threads | time [s] | speedup     | relative    |
+=========+==========+=============+=============+
| 1       | 27.152   |   1.0       |   n/a       |
+---------+----------+-------------+-------------+
| 4       |  6.100   |   4.5       |   4.48      |
+---------+----------+-------------+-------------+
| 8       |  3.176   |   8.5       |   1.92      |
+---------+----------+-------------+-------------+
| 16      |  1.669   |  16.3       |   1.90      |
+---------+----------+-------------+-------------+
| 32      |  0.921   |  29.5       |   1.81      |
+---------+----------+-------------+-------------+
| 64      |  0.601   |  45.2       |   1.52      |
+---------+----------+-------------+-------------+
| 128     |  0.524   |  51.8       |   1.14      |
+---------+----------+-------------+-------------+
| 256     |  0.458   |  59.3       |   1.14      |
+---------+----------+-------------+-------------+

Image size: 32768 x 32768

+---------+----------+-------------+
| threads | time [s] | relative    |
+=========+==========+=============+
|  16     | 102.586  | n/a         |
+---------+----------+-------------+
|  32     |  53.710  | 1.91        |
+---------+----------+-------------+
|  64     |  27.909  | 1.92        |
+---------+----------+-------------+
| 128     |  18.946  | 1.47        |
+---------+----------+-------------+
| 256     |  13.693  | 1.37        |
+---------+----------+-------------+
