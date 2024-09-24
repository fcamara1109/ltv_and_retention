This repository contains queries made in Google Big Query to calculate MAU, MRR, retention rate month-over-month, quick ratio, and also cohorts including LTV. It is based upon Jonathan Hsu's 2015 Medium posts:
* https://medium.com/swlh/diligence-at-social-capital-part-1-accounting-for-user-growth-4a8a449fddfc 
* https://medium.com/swlh/diligence-at-social-capital-part-2-accounting-for-revenue-growth-551fa07dd972 
* https://medium.com/swlh/diligence-at-social-capital-part-3-cohorts-and-revenue-ltv-ab65a07464e1 
* https://medium.com/swlh/diligence-at-social-capital-part-4-cohorts-and-engagement-ltv-80b4fa7f8e41 
* https://medium.com/swlh/diligence-at-social-capital-part-5-depth-of-usage-and-quality-of-revenue-b4dd96b47ca6
* https://medium.com/swlh/diligence-at-social-capital-epilogue-introducing-the-8-ball-and-gaap-for-startups-7ab215c378bc#.wxc2lc8dp 

The queries generate what’s needed for the charts from part 1 to 4.

The key difference is the added functionality of having filters.

In order to have month-over-month retention, I suggest calculating in Looker. The formulas are: `SUM(retained)/SUM(preceding_mau)` for MAU and `SUM(retained)/SUM(preceding_mrr)` for MRR.

Now, Quick Ratio I suggest adjusting with a -1 to better visualize in charts: 
* MAU: `-1 * (SUM(new) + SUM(resurrected)) / SUM(churned) -1`
* MRR: `-1 * (SUM(new) + SUM(resurrected) + SUM(expansion)) / (SUM(churned) + SUM(contraction)) -1`


As time goes by, I'll add answers to eventual technical questions here.
