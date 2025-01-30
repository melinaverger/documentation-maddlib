Evaluation
=====================

To import the following functions:

.. code-block:: console

   from maddlib import evaluation



Compute MADD
----------------

The ``evaluation.MADD()`` function which computes MADD depends on two other functions that are described below: ``evaluation.separate_pred_proba()`` and ``evaluation.normalized_density_vector()``.

.. py:function:: evaluation.MADD(h, X_test=None, pred_proba=None, sf=None, pred_proba_sf0=None, pred_proba_sf1=None, min_nb_points=50)

   Compute MADD.

   :param h: Bandwidth parameter (either a float :math:`\in \left]0, 1\right[` or ``'auto'`` for an automatic computation of the optimal bandiwdth).
   :type h: float or str

   :param X_test: Optional test set (without labels) on which to evaluate MADD. If ``X_test`` is given, ``preb_proba`` and ``sf`` are also expected to be given.
   :type X_test: pandas.DataFrame or None

   :param pred_proba: Optional predicted probabilities (associated to the test set ``X_test``) on which to evaluate MADD. If ``pred_proba`` is given, ``X_test`` and ``sf`` are also expected to be given.
   :type pred_proba: numpy.ndarray of shape (n, 1) or None

   :param sf: Optional sensitive feature name (from the test set ``X_test``) with which to evaluate MADD. If ``sf`` is given, ``X_test`` and ``pred_proba`` are also expected to be given.
   :type sf: str or None

   :param pred_proba_sf0: Optional predicted probabilities of group 0 with which to evaluate MADD. If ``pred_proba_sf0`` is given, ``pred_proba_sf1`` is also expected to be given.
   :type pred_proba_sf0: numpy.ndarray of shape (n, 1) or None

   :param pred_proba_sf1: Optional predicted probabilities of group 1 with which to evaluate MADD. If ``pred_proba_sf1`` is given, ``pred_proba_sf0`` is also expected to be given.
   :type pred_proba_sf1: numpy.ndarray of shape (n, 1) or None

   :param min_nb_points: Optional minimum number of points to consider in the bandwidth interval.
   :type min_nb_points: int or None

   :return: MADD result
   :rtype: float

.. py:function:: evaluation.separate_pred_proba(X, pred_proba, sf)

   Return the separated predicted probabilities according the sensitive feature.

   :param X: The feature set.
   :type X: pandas.DataFrame

   :param pred_proba: The predicted probabilities (of positive predictions).
   :type pred_proba: numpy.ndarray of shape (n, 1)

   :param sf: Sensitive feature name included in the feature set ``X``.
   :type sf: str

   :return: The couple of predicted probabilities separated (pred_proba_sf0, pred_proba_sf1)
   :rtype: couple of numpy.ndarray

.. py:function:: evaluation.normalized_density_vector(pred_proba_sfi, e)

   Compute the density vector for a group (:math:`D_{G_0}` or :math:`D_{G_1}`).

   :param pred_proba_sfi: The predicted probabilities (of positive predictions) for one group.
   :type pred_proba_sfi: numpy.ndarray of shape (n, 1)

   :param e: Bandwidth parameter. 
   :type e: float

   :return: The density vector
   :rtype: numpy.ndarray

Display MADD results
--------------------

To retrieve a list of random ingredients,
you can use the ``lumache.get_random_ingredients()`` function:

.. py:function:: evaluation.madd_plot(h, pred_proba_sf0, pred_proba_sf1, legend_groups, title, figsize=(12, 4))

   Return a plot of a visual approximation of the resulting MADD for graphical analysis.

   :param h: Bandwidth parameter (either a float :math:`\in \left]0, 1\right[` or ``'auto'`` for an automatic computation of the optimal bandiwdth).
   :type h: float or str

   :param pred_proba_sf0: The predicted probabilities of group 0 with which to evaluate MADD.
   :type pred_proba_sf0: numpy.ndarray of shape (n, 1)

   :param pred_proba_sf1: The predicted probabilities of group 1 with which to evaluate MADD. 
   :type pred_proba_sf1: numpy.ndarray of shape (n, 1)

   :param legend_groups: The name of the sensitive feature or the names of the two groups in a 2-tuple.
   :type legend_groups: str or 2-tuple

   :param title: The title of the graph (it could be the name of the model that outputs the predicted probabilities).
   :type title: str  

   :return: Plot
   :rtype: matplotlib.figure.Figure
