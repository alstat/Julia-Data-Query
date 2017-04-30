DataFramesMeta.jl for R's dplyr
--------------
I'm going to use R's dplyr as basis for demonstrating the use of DataFramesMeta.jl.
We'll try to reproduce the example in this site_.

.. _site: https://cran.rstudio.com/web/packages/dplyr/vignettes/introduction.html

Data: nycflights13
--------------
The data is available in the repository and we'll import this using the Request.jl_.

.. _Request.jl: https://github.com/JuliaWeb/Requests.jl

That is,

.. code-block:: julia

  using DataFrames
  using DataFramesMeta
  using Lazy
  using Requests

  url = "https://raw.githubusercontent.com/alstat/Julia-Data-Query/master/data-raw/flights.csv"

  flights = readtable(get_streaming(url));
  delete!(flights, :x);

We need to delete the column ``:x`` in the data frame since this is the index
and not a column of the original data and
