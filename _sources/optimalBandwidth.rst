Optimal bandwidth
=====================

To import the following functions:

.. code-block:: console

   from maddlib import optimal_bandwidth


Generate bandwidth search space
-------------------------------

.. py:function:: optimal_bandwidth.generate_bandwidths(N)

   Return ``N`` relevant values of bandwidth.

   :param N: The number of relevant and distinct values of h.
   :type N: int

   :return: The bandwidth 1-d vector
   :rtype: numpy.ndarray


Find the optimal bandwidth range
--------------------------------

.. py:function:: optimal_bandwidth.calculate_std(y, start, end)

   Return the standard deviation in the index interval [start, end] of y..

   :param y: The list of data in which to calculate the standard deviation.
   :type y: List or np.ndarray of shape (n, 1)

   :param start: The initial index.
   :type start: int

   :param end: The final index.
   :type end: int

   :return: The standard deviation
   :rtype: float

The ``optimal_bandwidth.find_stable_interval()`` depends on the previous one, ``optimal_bandwidth.calculate_std()``.

.. py:function:: optimal_bandwidth.find_stable_interval(h_list, madd_list, n0=None, n1=None, min_interval_length=None, min_nb_points=50)

   Return the bandwidth interval within which the MADD results are stable.

   :param h_list: The list of bandwidth values.
   :type h_list: List or np.ndarray of shape (n, 1)

   :param madd_list: The list of MADD results for each bandwidth values.
   :type madd_list: List or np.ndarray of shape (n, 1)

   :param n0: The number of samples in the group 0.
   :type n0: int

   :param n1: The number of samples in the group 1.
   :type n1: int

   :param min_interval_length: The minimum length for the bandwidth interval to consider.
   :type min_interval_length: float

   :param min_nb_points: The minimum number of points to consider in the bandwidth interval.
   :type min_nb_points: int

   :return: Dictionary of the results
   :rtype: dict

Display optimal bandwidth range
-------------------------------

.. py:function:: optimal_bandwidth.plot_stable_interval(h_list, madd_list, show_stable=True, indexes=None, show_order=False, n0=None, n1=None, zoom="None", legend=True, ylim=None)

   Return a plot of MADD results according to the bandwidth.

   :param h_list: The list of bandwidth values.
   :type h_list: List or np.ndarray of shape (n, 1)

   :param madd_list: The list of MADD results for each bandwidth values.
   :type madd_list: List or np.ndarray of shape (n, 1)

   :param show_stable: To show the stable interval or not.
   :type show_stable: boolean

   :param indexes: The indexes (initial, final) of the stable interval (to compute with ``find_stable_interval()``).
   :type indexes: tuple

   :param show_order: To show informational bandwidth values or not.
   :type show_order: boolean

   :param n0: The number of samples in the group 0.
   :type n0: int

   :param n1: The number of samples in the group 1.
   :type n1: int

   :param zoom: To specify some zoom options.
   :type zoom: str or 2-tuple

   :param legend: To show the legend or not.
   :type legend: boolean

   :param ylim: To specify the y-axis values to show.
   :type ylim: 2-tuple

   :return: Plot
   :rtype: matplotlib.figure.Figure
