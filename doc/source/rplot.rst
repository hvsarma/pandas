.. currentmodule:: pandas
.. _rplot:

.. ipython:: python
   :suppress:

   import numpy as np
   np.random.seed(123456)
   from pandas import *
   import pandas.util.testing as tm
   randn = np.random.randn
   np.set_printoptions(precision=4, suppress=True)
   import matplotlib.pyplot as plt
   plt.close('all')

*******************
Plotting with RPlot
*******************

RPlot is a trellis plotting interface for pandas. It works by splitting the
data set in to groups to be plotted separately. It also arranges the plots
in a rectangular lattice. There are also features to assign DataFrame 
attributes to graphical features of a plot. It uses matplotlib for plotting.