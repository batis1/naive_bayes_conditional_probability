# -*- coding: utf-8 -*-
"""
Created on Fri Apr 23 15:24:19 2021

@author: batis 18511160002
"""
import pandas

df = pandas.read_excel("flighDelay_wingo.xlsx")
p_onTime = df['delay'].tolist().count('ontime')/len(df)
p_delay = df['delay'].tolist().count('delayed')/len(df)
print(p_onTime)
print(p_delay)
print("*"*60)
for i in range(5):
    print(df.groupby('delay')['sch_time'].value_counts() / df.groupby('delay')['sch_time'].count())
    print(df.groupby('delay')['carrier'].value_counts() / df.groupby('delay')['carrier'].count())
    print(df.groupby('delay')['dest'].value_counts() / df.groupby('delay')['dest'].count())
    print(df.groupby('delay')['origin'].value_counts() / df.groupby('delay')['origin'].count())
    print(df.groupby('delay')['dayweek'].value_counts() / df.groupby('delay')['dayweek'].count())
