Contributed Examples
==============
The following contains examples contributed by the community


This section contains examples using DataFramesMeta.jl package.

.. code-block:: R

library(dplyr)

women_new <- rbind(women, c(NA, 1), c(NA, NA))
women_new %>%
  filter(height %>% complete.cases) %>%
  mutate(sector = character(n()),
         sector = replace(sector, height >= 0 & height <= 60, "1"),
         sector = replace(sector, height >= 61 & height <= 67, "2"),
         sector = replace(sector, height >= 68 & height <= 72, "3"))


Transform
-----------------
1. This example is available in this link_. We want to reproduce the following R codes:

  **Solution: DataFramesMeta.jl**
  In Julia's DataFramesMeta we can do this as follows:

.. code-block:: julia

@> begin
women_new
@where !isna(:Height)
@transform(
  Class = @> begin
    function (x)
       0 <= x <= 60 ?  1 :
      61 <= x <= 67 ?  2 :
      68 <= x <= 72 ?  3 :
      NA
    end
    map(:Height)
  end
)
end

  And if we want to deal with the complete data without removing the ``NA``. Then the following
  is the remedy:

.. code-block:: julia

@> begin
women_new
@transform(
  Class = @> begin
    function (x)
      isna(x)       ? NA :
       0 <= x <= 60 ?  1 :
      61 <= x <= 67 ?  2 :
      68 <= x <= 72 ?  3 :
      NA
    end
    map(:Height)
  end
)
end

  **Solution: Query.jl**
  Equivalently, we can proceed using Query.jl as follows:

.. code-block:: julia

@from i in women_new begin
    @where !isnull(i.Height)
    @select {
      i.Height, i.Weight,
      class = 0 <= i.Height <= 60 ?  1 :
             61 <= i.Height <= 67 ?  2 :
             68 <= i.Height <= 72 ?  3 :
              0
    }
    @collect DataFrame
end

  And if we are to consider all observations without removing the ``NA`` then we can do

.. code-block:: julia

@from i in women_new begin
    @select {
      i.Height, i.Weight,
      class = 0 <= i.Height <= 60 ?  1 :
             61 <= i.Height <= 67 ?  2 :
             68 <= i.Height <= 72 ?  3 :
              0
    }
    @collect DataFrame
end

Filter
----------------

Summarize
----------------

Join
----------------

.. _link: https://discourse.julialang.org/t/julia-dataframesmeta-transformation/3435
