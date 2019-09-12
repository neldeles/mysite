+++
categories = []
date = "2019-09-11T16:00:00+00:00"
tags = []
title = "Dateoffset to arrive at SLA date in Pandas"

+++
Offset a date, excluding holidays and non-working days

<!--more-->

\`\`\`python

import pandas as pd

import numpy as np

from datetime import datetime

\# load holidays in yyyy-mm-dd

dates = \['2018-01-01', '2018-01-02', '2018-02-16', '2018-02-25', '2018-03-29', '2018-03-30', '2018-03-31', '2018-04-09', '2018-05-01', '2018-06-12', '2018-06-15', '2018-08-21', '2018-08-27', '2018-11-01', '2018-11-02', '2018-11-30', '2018-12-24', '2018-12-25', '2018-12-30', '2018-12-31'

,'2019-12-31'

,'2019-12-30'

,'2019-12-25'

,'2019-12-24'

,'2019-12-08'

,'2019-11-30'

,'2019-11-01'

,'2019-08-26'

,'2019-08-21'

,'2019-08-12'

,'2019-06-12'

,'2019-06-05'

,'2019-05-01'

,'2019-04-20'

,'2019-04-19'

,'2019-04-18'

,'2019-04-09'

,'2019-02-25'

,'2019-02-05'

,'2019-01-01'\]

holidays = np.array(dates, dtype='datetime64\[D\]')

\# typecasting

df\['start_clock'\] = df\['start_clock'\].values.astype('datetime64\[D\]')

sla_offset = lambda n: pd.tseries.offsets.CustomBusinessDay(n, weekmask='Mon Tue Wed Thu Fri Sat', holidays=holidays) 

df\['sla_date'\] = df\['start_clock'\] + df\['sla_days'\].apply(sla_offset)

\`\`\`