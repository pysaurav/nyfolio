+++
date = "2020-08-19"
title = "Pandas Optimized Code Snippets"
description = "Will gradually append optmized pandas code in this post"
tags = ["pandas", "optimized","data"]
+++

Here are the pandas snippets that will make data cleaning easier. These will make the process easier and faster.

#Note: I will gradually update the list
## 1. To clean numbers and text inside brackets from a column using regex

```
import pandas as pd
import re

df = pd.DataFrame({"Code":["EE","NP","USA","ES"],"Country":["Estonia{EE}","Nepal123","United States Of America(USA)","Spain"]})
df
```
![Output](/library/pandas/numberbracket.png)
```
df['Country'] = df['Country'].replace(r"[\(\[\{].*?[\)\]\}]|[^a-zA-Z ]", "",regex=True)
df
```
![Output](/library/pandas/numberbracket_clean.png)
