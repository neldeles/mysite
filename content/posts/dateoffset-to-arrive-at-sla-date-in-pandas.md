+++
categories = ["tutorial"]
date = "2019-09-11T16:00:00+00:00"
tags = ["pandas"]
title = "Dateoffset to arrive at SLA date in Pandas"

+++
Offset a date, excluding holidays and non-working days

<!--more-->

```
import pandas as pd
import numpy as np
from datetime import datetime

# load holidays in yyyy-mm-dd

dates = ['2018-01-01', '2018-01-02', '2018-02-16', '2018-02-25']

holidays = np.array(dates, dtype='datetime64[D]')

# typecasting

df['start_clock'] = df['start_clock'].values.astype('datetime64[D]')

sla_offset = lambda n: pd.tseries.offsets.CustomBusinessDay(n, weekmask='Mon Tue Wed Thu Fri Sat', holidays=holidays)

df['sla_date'] = df['start_clock'] + df['sla_days'].apply(sla_offset)
```
