This repository contains queries made in Google Big Query to calculate MAU, MRR, retention rate month-over-month, quick ratio, and also cohorts including LTV. It is based upon Jonathan Hsu's 2015 Medium posts: https://medium.com/swlh/diligence-at-social-capital-part-1-accounting-for-user-growth-4a8a449fddfc.

The difference is the added functionality of having filters.

In order to have month-over-month retention, I suggest calculating in Looker. The formulas are: `SUM(retained)/SUM(preceding_mau)` for MAU and `SUM(retained)/SUM(preceding_mrr)` for MRR.

Now, Quick Ratio I suggest adjusting with a -1 to better visualize in charts: 
* MAU: `-1 * (SUM(new) + SUM(resurrected)) / SUM(churned) -1`
* MRR: `-1 * (SUM(new) + SUM(resurrected) + SUM(expansion)) / (SUM(churned) + SUM(contraction)) -1`


As time goes by, I'll add answers to eventual technical questions here.
