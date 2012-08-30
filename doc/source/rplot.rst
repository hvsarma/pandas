.. currentmodule:: pandas
.. _rplot:

.. ipython:: python
   :suppress:

   import numpy as np
   from pandas import read_csv
   np.random.seed(123456)
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

A basic plot 

.. ipython:: python

    import pandas.tools.rplot as rplot
    data = read_csv('data/iris.data', sep=',')
    plot = rplot.RPlot(data, x='SepalLength', y='SepalWidth')
    plot.add(rplot.GeomPoint(colour=rplot.ScaleGradient('PetalLength', colour1=(0.0, 1.0, 0.5), colour2=(1.0, 0.0, 0.5)), 
            size=rplot.ScaleSize('PetalWidth', min_size=10.0, max_size=200.0),
            shape=rplot.ScaleShape('Name')))

    @savefig rplot_iris.png width=6in
    plot.render(plt.gcf())