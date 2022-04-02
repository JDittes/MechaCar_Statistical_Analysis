# MechaCar_Statistical_Analysis
Practice with R

## Linear Regression to Predict MPG
When I used MPG as the independent variable, I found that several aspects of the cars' bodies were statistically significant. The **vehicle_length** variable had a probability (pr(>|T|)) of 0.0000000000026 and the **ground_clearance** had a probability of 0.000000052. These p-values were extremely low so we reject the null hypothesis and state that there is a statistically probabliy relationship between these variables.

Both **vehicle_length** (6.27) and **ground_clearance** (3.55) have significant slopes. Vehicle length has more to do with miles per gallon than clearance does. These can be found in the "Estimate" column. All other variables have negligible slope.

This linear model predicts the mile per gallon (mpg) of fubure MechaCar cars quite effectively. If designers want to design more fuel-efficient cars, they should look at reducing length and ground clearance.
![MPG and other aspects of body style](https://github.com/JDittes/MechaCar_Statistical_Analysis/blob/main/deliverable_1.png)

## Summary Statistics on Suspension Coils
When I looked at the mean PSI of the full sample of suspension coils, I found the PSI to be similar, with a mean of 1,499 PSI and a standard deviation of 7.89. When I divide the standard deviation by the mean, the coefficient of variation is 0.005. This shows a very low amount of variation among all the measures in the dataset.
![Summary of all coils](https://github.com/JDittes/MechaCar_Statistical_Analysis/blob/main/d2_total_summary.png)

Next I looked at the variation among the 3 different lots of suspension coils. Among the three lots, there was much greater range, from 170.29 to 7.47 to 0.97.  This closer look at the data showed a wide range of variance. This is a case where a broader sample--in this case, the whole set of data--shows a much more accurate description of the data with minimal variance. 
![Lot summaries](https://github.com/JDittes/MechaCar_Statistical_Analysis/blob/main/d2_lot_summary.png)

## T-Tests on Suspension Coils
I compared the PSI of all three lots of suspension coals with the industry average, using the code, ``` t.test(total_summary, mu = 1500)```. I already had the data from the full dataset in my variable, **total_summary**, and I just had to compare that with the industry standards
The result was a p-value of 0.1815. This shows that the differences between the current sample and the industry standard is not significant.
![T-test results](https://github.com/JDittes/MechaCar_Statistical_Analysis/blob/main/d3_ttest.png)

I ran a second set of t-tests on the subsets from lots 1, 2, and 3 using the code ```t.test(subset(sus_coil,Manufacturing_Lot=='Lot3')$PSI, mu = 1500)```. It's interesting, the p value of Lot1 was 1. Clearly there was absolutely no difference between the subset and the standard mean. My Lot2 sample returned a p-value of 0.61, well within standard. Lot3 had a p value of 0.042, slightly below the 0.05 cutoff for p-value significance.
![T-tests for samples](https://github.com/JDittes/MechaCar_Statistical_Analysis/blob/main/d3__sample_ttests.png)

Had Lot3 been the only sample I studied, I might have rejected the null hypothesis. However, with the accurate measures of lots 1 & 2--along with the p-value of the whole sample, I'm confident this return was an outlier. The sample lies within range of the industry standard.

## Study Design: MechaCar vs Competition
With fuel prices rising, more car buyers are looking to electric cars as they plan their next auto purchases. My sister just bought a Tesla. The one thing she _doesn't_ complain about with her car is the gas mileage. It is infinite. (She complains about the apps a little, but she loves her new car.)

One barrier to the purchase of electric cars, however, is the need for safety. Electric cars--along with fuel-efficient, gas-powered compact cars--are typically smaller than the sedans and SUVs that have been staples of the American highway for many years. One reason a family may give for driving two toddlers around in a minivan or SUV instead of a compact car would be 'safety.'

The first challenge would be finding an accurate source of data. I could use the crash-test data provided by the manufacturers, but there are a couple problems with this: first, the data may be _biased_ to enhance the reputation of the manufacturers' own models; secondly, the data may not share the same variables as another manufacturer. As car companies are based in countries around the world, this would give me the extra step of cleaning the data: factoring kilometers per gallon with miles per gallon, for example.

I think the best source of safety data would be the US National Highway Traffic Safety Administration (NHTSA). They have a database called the [Crashworthiness Data System](https://www.nhtsa.gov/national-automotive-sampling-system/crashworthiness-data-system) which investigates traffic accidents around the country for a variety of factors. It provides free data in a number of different formats for researchers and statisticians. Another useful source is the [Insurance Institute for Highway Safety](https://www.iihs.org/)

There are several streams of data I could use to compare the vehicles. IIHS offers ratings on **Crashworthiness** and **Crash Avoidance and Mitigation** (the ability to warn drivers and prevent an impending accident.  NTSA has a different scale, ranking cars on **Overall Rating**, **Frontal crash**, **Side Crash**, and **Rollover**. The NHTSA uses a five-star scale, however, while the IIHS uses a four-point scale.

This would be numerical data for my study.

I would first set up a table listing a selected set of electrical vehicles, along with similar-sized gas-powered, cars for comparison. Depending on the amount of time I had, I would probably utilize the simpler IIHS data.

My null hypothesis in this case would be: "there is no significant difference in safety between electric cars and gas-powered cars." The alternate hypothesis would be "there is a significant difference in safety between electric and gas-powered cars."

Using **subsets** I would group the cars by engine types, then I would find the mean, max, and minimum values of the groups. 

Next I would gauge the variance of the ratings in the data set. If there were large varations in either of the subsets, I would need to go back and add data to the subsets with high variance. For example, if I had six electric cars and had a variation higher than 0.05, I would increase the number of electric cars in the set.

Once I had valid data, I would assess for p-values between the two data sets, searching to see if there were significant difference. If there were no significant difference, I would fail to reject the null, meaning that electric cars were just as safe as electric cars. 

If the p-values were low enough to indicate difference, I would be able to tell which cars were safer, gas or electric.

No matter how the results for the groups worked out, I would probably repeat the test with each of the electric cars, comparing them with the mean values of the gas-powered cars to see if any particular models might have significant safety advantages.
