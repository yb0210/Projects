

```python
%config IPCompleter.greedy = True
```


```python
import pandas as pd
import numpy as np
from parser import *

# %matplotlib inline
```


```python
#Data ingestion
n_temp = int(input('No. of Entries'))
raw_temp = input('Enter the diffrent tempratures(with space sepration)')
temp = raw_temp.split(' ') #Parsing data into list
temp = [int(x) for x in temp]
```

    No. of Entries10
    Enter the diffrent tempratures(with space sepration)-1 5 4 2 3 5 -5 23 5 4
    


```python
z = []
for x in range(len(temp)):
    ans = 0-temp[x] 
    z.append(abs(ans)) # finding the closest range of data

rel = z.index(min(z))
for x in range(len(temp)):
    for y in range(len(temp)):
        if (z[x] == z[y] and min(z) == z[x]):
            rel = temp.index(max(temp[x],temp[y]))
            temp_ans = max(temp[x],temp[y])
        else:
            temp_ans = temp[rel]

print('The temprature entered at',rel+1,'position is closest to zero i.e',temp_ans)

```

    The temprature entered at 1 position is closest to zero i.e -1
    
