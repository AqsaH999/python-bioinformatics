# Week 1 - Stats Notes

## What is a p-value?
A p-value is the probability of seeing a result this extreme (or more extreme) if the null hypothesis were true (i.e., if there's no real effect). It ranges from 0 to 1. A small p-value means the data would be very surprising under the null, suggesting a real effect exists. It does NOT measure effect size — only how surprising the result is.


## What does "statistically significant" mean?
A result is called "statistically significant" if the p-value is below a chosen threshold (commonly 0.05). This means there's less than a 5% chance of seeing data this extreme if the null hypothesis were true. It suggests the result is unlikely due to random chance alone. However, "significant" doesn't always mean "important" — tiny effects can be significant with enough data.


## Why is multiple testing a problem?
When you run many statistical tests (e.g., 20,000 genes in RNA-seq), you expect some false positives even when nothing is real. At p < 0.05, you'd expect 5% false positives — so out of 20,000 tests, ~1,000 would be "significant" by chance alone. This is why we use corrections like FDR (Benjamini-Hochberg) to control the false positive rate when testing many hypotheses at once.