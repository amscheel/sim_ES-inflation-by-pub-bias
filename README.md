# sim_ES-inflation-by-pub-bias

This is an R script for a minimal simulation of the influence of extreme publication bias (only significant results get published) on effect sizes. I wrote this for a [workshop](https://osf.io/pg29z/) on open science I gave at the University of Göttingen on 9th June 2017. 

The first part of the script ("adjust these values", line 11-16) lets you pick a true effect size (d) and sample size (n - this is actually the group size for the two-group experiments we will simulate). After setting these, run the script down to line 61. This will simulate 10,000 two-sample t-tests with the group size you just entered, drawing from a population in which the effect size you entered is true.

Running line 65 and 66 will give you two outputs: **dmin** is the smallest *significant* effect size from the 10,000 effects you simulated. If this number is larger than the true effect size you set at the beginning, it means that you had less than 50% power to detect the true effect size (because your sample size was too small). **dmean** is the average of the effects that came up significant.

The last two lines of code, line 70 and 71, will give you two plots: **dallplot** will show you all the effects you simulated. You will see a normal distribution centred around the true effect size you set at the beginning. The true effect is marked by a red vertical line. **dsigplot** shows you the same plot but takes away all the effects that were not significant. If the studies you simulated were underpowered (less than 50% power for the true effect size), the red line will now be standing alone in empty space. If you are running the script in RStudio, you can use the small arrows at the top of the plot panel to switch back and forth between the two plot to see the immediate effect of extreme publication bias (suppressing all non-significant effects). 

This simulation shows how publication bias inflates effect sizes: Unless power is high, significant effects tend to overestimate the true effect size. Only looking at significant effects will give us a distorted view of the true effect.
