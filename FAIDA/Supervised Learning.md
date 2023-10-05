Supervised Learning is a subset of [[ml|ML]] which is adopted when all the variables which are in the equation are already known.

Let's understand this with a simple example.

Let's say a farmer wants to grow crops, he can grow the following crops:  
  - carrots
  - potatos
  - onions
  - raddish
  - sweet potato

For each of the crops, let's say he has some data in tabular format which has the following columns

|plant|seed/sapling count|demand|supply|seed/sapling cost|required rainfall|required sunlight|required fertilizer|required nutrients|land degradation factor|area per plant|
|:---:|:----------------:|:----:|:----:|:---------------:|:---------------:|:---------------:|:-----------------:|:----------------:|:---------------------:|:------------:|

He also has the table of the what he and his peers used in previous years which has the above data, and the profitability it held and the land degradation which happened

In total, let's say he has around 1 million such tables.

Now, he wants to 
1. maximize his profit(obviously)
2. minimize his land degradation

for this table.

The farmer can use a supervised learning model, to calculate this. 
