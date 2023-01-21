# Topsis_102017182

# Topsis
# Technique for Order Preference by Similarity to Ideal Solution (TOPSIS)
In a general sense, it is the aspiration of human being to make "calculated" decision in a position of
multiple selection. In scientific terms, it is the intention to develop analytical and numerical methods that take into
account multiple alternatives with multiple criteria.
TOPSIS (Technique for Order Preference by Similarity to Ideal Solution) is one of the numerical
methods of the multi-criteria decision making


## Installation
Use the package manager [pip](https://pip.pypa.io/en/stable/) to install the package
```
pip install Topsis_102017182_sandhya_goyal
```


## Import

```
from Topsis_102017182_sandhya_goyal import topsis
```

## Usage
topsis module has a function names get_score which takes 3 arguements as:
1. dataframe - It is a pandas dataframe which has atleast 3 columns(including the first column with names). It should only have numerical values. Any non-numerical value should be encoded before passing it to function.
2. weights - It is a string of comma(,) separated numbers which tell the weight of each criteria.
3. impacts - It is a string of comma(,) separated + and - sign showing the impact of criteria on decision making.

The function return the original pandas dataframe with 2 more columns added, which are Topsis Score and Rank.
```
topsis.get_score(dataframe,weights,impacts)
```


## Example

data.csv (Input):

|contestent|sur|tal|lah|pitch|sharpness|
|------|---|----|-------|-------|-----|
|a|4|18|6.5|35|15|
|b|6|14|4|38|19|
|c|6|12|5|42|20|
|d|8|26|7|50|25|
|e|3|14|6|40|14|


```
import pandas as pd
df = pd.read_csv('data.csv')
weights = "+,+,+,+,+"
impacts = "1,1,1,1,1"
print(topsis.get_score(df,weights,impacts))
```

Output:

|contestent|sur|tal|lah|pitch|sharpness|output|
|--|------|----|--------|--------|-------|-------|
|a|4|18|6.5|35|15|3|
|b|6|14|4|38|19|4|
|c|6|12|5|42|20|2|
|d|8|26|7|50|25|1|
|e|3|14|6|40|14|5|
