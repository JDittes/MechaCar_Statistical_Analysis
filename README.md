# MechaCar_Statistical_Analysis
Practice with R

## Linear Regression to Predict MPG
When I used MPG as the independent variable, I found that several aspects of the cars' bodies were statistically significant. The **vehicle_length** variable had a pr(>|T|) value of 0.0000000000026 and the **ground_clearance** had a value of 0.000000052. These probablility of error rations were extremely low, rejecting the null hypothesis and proving >99% significance.
![MPG and other aspects of body style](https://github.com/JDittes/MechaCar_Statistical_Analysis/blob/main/deliverable_1.png)

## Summary Statistics on Suspension Coils
When I looked at the suspension coils, I found the PSI to be similar, with a mean of 1,499 PSI and a standard deviation of 7.89. When I divide the standard deviation by the mean, the coefficient of variation is 0.005. This shows a very low amoung of variation among all the measures in the dataset.
![Summary of all coils](https://github.com/JDittes/MechaCar_Statistical_Analysis/blob/main/d2_total_summary.png)

Next I looked at the variation among the 3 different lots of suspension coils. Among the three lots, there was much greater variance, ranging from 170.29 to 7.47 to 0.97.  This closer look at the data showed a wide range of variance. This is a case where a broader sample--in this case, the whole set of data--shows a much more accurate description of the data with minimal variance. 
![Lot summaries](https://github.com/JDittes/MechaCar_Statistical_Analysis/blob/main/d2_lot_summary.png)

## T-Tests on Suspension Coils
I compared the PSI of all three lots of suspension coals with the industry average, using the code, ``` t.test(total_summary, mu = 1500)```. I already had the data from the full dataset in my variable, **total_summary**, and I just had to compare that with the industry standards.

The result was a p-value of 0.1815. This shows that the differences between the current sample and the industry standard is not significant.
![T-test results](https://github.com/JDittes/MechaCar_Statistical_Analysis/blob/main/d3_ttest.png)

