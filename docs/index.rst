Data Query in Julia
==============
In data analysis, one of the challenges faced by statisticians/data scientists/researchers is
the data cleaning. And for most of us coming from R and Python, we enjoyed the vast resources
of the documentations of our favorite packages, such as `R's dplyr`_ and `Python's Pandas`_. And most
of our problems often have answers already on forums such as `Stack Overflow`_. Unfortunately,
this is not the case for Julia, but we do have an active community on places such
as Github_, Gitter_ and `Julia Discourse`_. Of course we like to invite more users and grow
the community even bigger. This is the motivation of the project, by giving newcomers a good place to start.
The project aims to provide compilation of examples for data queries in Julia. The benefit of
doing this is that we can track the limitations of the current data query packages and further
improve it. I do encourage readers to contribute their examples for references.
We'll feature this at the Contributed section of the two data query packages, namely the DataFramesMeta.jl_
and the Query.jl_.

Specifically, the documentation proceeds by reproducing the examples in `RStudio's dplyr documentation`_
using both DataFramesMeta.jl_ and Query.jl_.

Contents
-------------

.. toctree::
    :maxdepth: 2

    dplyr.rst
    contrib.rst

Contributors
-------------
Prepared and maintain by Al-Ahmadgaid B. Asaad (twitter_, blog_) and `Other Contributors`_.

.. _twitter: https://twitter.com/alasaadstat
.. _blog: https://alstatr.blogspot.com/
.. _DataFramesMeta.jl: https://github.com/JuliaStats/DataFramesMeta.jl
.. _DataFrames.jl: https://github.com/JuliaStats/DataFrames.jl
.. _Query.jl: https://github.com/davidanthoff/Query.jl
.. _Stack Overflow: http://stackoverflow.com/
.. _Other Contributors: https://github.com/alstat/Julia-Data-Query/graphs/contributors
.. _R's dplyr: https://cran.rstudio.com/web/packages/dplyr/vignettes/introduction.html
.. _Python's Pandas: http://pandas.pydata.org/
.. _Github: https://github.com/JuliaLang/julia
.. _Gitter: https://gitter.im/JuliaLang/julia
.. _Julia Discourse: https://discourse.julialang.org/
.. _RStudio's dplyr documentation: https://cran.rstudio.com/web/packages/dplyr/vignettes/introduction.html
