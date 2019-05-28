+++
categories = ["tutorial"]
date = "2019-05-28T10:00:00+00:00"
tags = ["pandas"]
title = "Flattening JSON in Dataframe with missing values"

+++
I faced a problem similar to [this](https://www.reddit.com/r/learnpython/comments/7g6tyo/splitting_a_column_in_pandas_that_has_some_null/) guy. Pandas kept spitting out the error `ValueError: Columns must be same length as key`.

While his solution isn't the most elegant or efficient, it does the job.

In my case, since the column with possible missing values wasn't a column I needed, I just used the [`drop`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.drop.html) function.

Main takeaway is before trying to find a solution, stop and think things through first. *Do you really need the data that is causing the issue?* If not, `drop` it. :) 