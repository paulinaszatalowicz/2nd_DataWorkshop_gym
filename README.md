##### Let's say we have a list of clients in Word and we want to order it. I used Pandas to make a table.

```Python
import pandas as pd
df = pd.DataFrame()
full_names = [
    "Jan Nowak",
    "Agata Nowak",
    "Michał Kowalczyk",
    "Mateusz Adamczyk",
    "Katarzyna Kowalczyk",
]
df["full_name"]= full_names

df["full_name"].str.split(expand=True)
```

##### I got a split of names, but the function left the columns titled "0" and "1" by default.

```Python
df = pd.DataFrame()
df["full_name"]= full_names

df["full_name"].str.split(expand=True).rename(
    columns = {0:"first_name", 1:"last_name"})
```

##### Now it is perfectly fine, the colums have their custom names
