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
I compared the PSI of all three lots of suspension coals with the industry average, using the code, ``` t.test(total_summary, mu = 1500)```. I already had the data from the full dataset in my variable, **total_summary**, and I just had to compare that with the industry standards
The result was a p-value of 0.1815. This shows that the differences between the current sample and the industry standard is not significant.
![T-test results](https://github.com/JDittes/MechaCar_Statistical_Analysis/blob/main/d3_ttest.png)

## Study Design: MechaCar vs Competition
With fuel prices rising, more car buyers are looking to electric cars as they plan their next auto purchases. My sister just bought a Tesla. The one thing she _doesn't_ complain about with her car is the gas mileage. It is infinite. (She complains about the apps a little, but she loves her new car.)

One barrier to the purchase of electric cars, however, is the need for safety. Electric cars--along with fuel-efficient, gas-powered compact cars--are typically smaller than the sedans and SUVs that have been staples of the American highway for many years. One reason a family may give for driving two toddlers around in a minivan or SUV instead of a compact car would be 'safety.'

The first challenge would be finding an accurate source of data. I could use the crash-test data provided by the manufacturers, but there are a couple problems with this: first, the data may be _biased_ to enhance the manufacturers' own models; secondly, the data may not share the same variables as another manufacturer. As car companies are based in countries around the world, this would give me the extra step of cleaning the data: factoring kilometers per gallon with miles per gallon, for example.

I think the best source of safety data would be the US National Highway Traffic Safety Administration (NTSA). They have a database called the [Crashworthiness Data System](https://www.nhtsa.gov/national-automotive-sampling-system/crashworthiness-data-system) which investigates traffic accidents around the country for a variety of factors. It provides free data in a number of different formats for researchers and statisticians. Another useful source is the {Insurance Institute for Highway Safety](https://www.iihs.org/)

There are several streams of data I could use to compare the vehicles. IIHS offers ratings on **Crashworthiness** and **Crash Avoidance and Mitigation** (the ability to warn drivers and prevent an impending accident.  NTSA has a different scale, ranking cars on **Overall Rating**, **Frontal crash**, **Side Crash**, and **Rollover**. The NHTSA uses a five-star scale, however, while the IIHS uses a four-point scale.

This would be numerical data for my study.

I would first set up a table listing a selected set of electrical vehicles, along with a gas-powered, four-door sedan for comparison. Depending on the amount of time I had, I would probably utilize the simpler IIHS data.

My null hypothesis in this case would be: "there is no significant difference in safety between electric cars and gas-powered cars." The alternate hypothesis would be "there is a significant difference in safety between electric and gas-powered cars."

I need to find p-values to determine the statistical significance
