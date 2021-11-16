# MechaCar_Statistical_Analysis
R Script Challenge

# Overview of the Project
```AutosRUs’ newest prototype, the MechaCar, is suffering from production troubles that are blocking the manufacturing team’s progress. It has to be review the production data for insights using data analytics.

The following shall be done in order to help the manufacturing team:

  - Perform multiple linear regression analysis to identify which variables in the dataset predict the mpg of MechaCar prototypes
  - Collect summary statistics on the pounds per square inch (PSI) of the suspension coils from the manufacturing lots
  - Run t-tests to determine if the manufacturing lots are statistically different from the mean population
  - Design a statistical study to compare vehicle performance of the MechaCar vehicles against vehicles from other manufacturers. For each statistical analysis, you’ll write a summary interpretation of the findings.
 ```
## Linear Regression to Predict MPG

## ```Output from the linear regression```

![Delirable_1](https://user-images.githubusercontent.com/86028032/141878696-037e1e1f-2270-4eb0-b644-34e1d119ec31.PNG)

Which variables/coefficients provided a non-random amount of variance to the mpg values in the dataset?
- Looking at the Correlation Coefficient Matrix, there are no variables that share what is considered a strong correlation (1>= absolute value "r" >= 0.7), as shown above.

Correlation Coefficient Matrix
"MPG" and "Vehicle Length" share a moderate correlation of 0.61, which is the strongest of all variables, with "MPG" and "Ground Clearance" coming in second at a weak-moderate correlation level of 0.33.
When we square the Vehicle Length coefficient, we get R-squared of approximately 0.37. This indicates that Vehicle length will only predict about 37% of mpg observations.

Is the slope of the linear model considered to be zero? Why or why not?
- P-value of our linear regression analysis is 2.63e-06, which is much smaller than our assumed significance level of 0.05%. 

Does this linear model predict mpg of MechaCar prototypes effectively? Why or why not?
- R-squared of approximately 0.3715, indicates that the multiple linear regression will predict 37.15% of mpg observations, it's a low prediction, so it has to realize further analysis in order to create a model that ptedicts mpg.


## ```Summary Statistics on Suspension Coils```

The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not?

### Total Summary Table
![Total_summary](https://user-images.githubusercontent.com/86028032/141879879-bf1fa669-941e-446a-9adf-4c9edf9b2e88.PNG)

According the Total Summary table, PSI Variance for all lots combined is 62.29 pounds per square inch. This satisfies the design specification requirements.

### Lot Summary Table
![lot summary](https://user-images.githubusercontent.com/86028032/141879884-5835e49f-a1a6-45a0-a468-6c5ed32ff377.PNG)

According the Lot Summary table, PSI Variance for Lots 1 thru 3 yield 0.98, 7.47 and 170.29 pounds per square inch respectively.

We can appreciate that lot 3 is the only lot that exceeds the 100lb weight capacity. However, looking at the median and mean, we can see that the data is Left Skewed which indicates there is a higher probability that lower weights exist at this location than others. This is evidenced by the Standard Deviation being higher for this location as well. we required further analysis in order to review this information

## ```T-Tests on Suspension Coils```

We want to determine if the PSI across all manufacturing lots is statistically different from the population mean of 1,500 pounds per square inch.
Using R, we will perform t-tests to calculate the p-value and compare it against a significance level of 0.05.

![Test_All_Lots](https://user-images.githubusercontent.com/86028032/141881232-56a2a26c-0abd-4416-914a-c9f4dacf70cb.PNG)

At a significance level of the common 0.05 percent, our p-value of 0.06 is above the significance level. Therefore, we do not have sufficient evidence to reject that there is a statistical difference between All Manufactuting lots and the population mean.

![Test_Lot_1](https://user-images.githubusercontent.com/86028032/141880849-5d225c7a-206c-4c67-ae90-489d75983fd4.PNG)

At a significance level of the common 0.05 percent, our p-value of 1.0 is above the significance level. Therefore, we do not have sufficient evidence to reject that there is a statistical difference between Lot 1 and the population mean. The two means are statistically similar.

![Test_Lot_2](https://user-images.githubusercontent.com/86028032/141880846-b6b05d54-9858-4bc8-872f-453f88e727e9.PNG)

At a significance level of the common 0.05 percent, our p-value of 0.61 is above the significance level. Therefore, we do not have sufficient evidence to reject that there is a statistical difference between Lot 2 and the population mean. The two means are statistically similar.

![Test_Lot_3](https://user-images.githubusercontent.com/86028032/141880847-b120105d-72a2-4ed5-91ba-ad18b00256a4.PNG)

At a significance level of the common 0.05 percent, our p-value of 0.042 is below the significance level. There is sufficient statistical evidence to reject that there is a statistical difference between Lot 3 and the population mean.

## ```Study Design: MechaCar vs Competition```

Statistical study to compare performance of the MechaCar vehicles against performance of vehicles from other manufacturers.

Metrics
The metrics to test are both city and highway fuel efficiency.

Hypothesis
Null: MechaCar has the same fuel efficiency for each cylinder class.

Statistical Tests
Use linear regression and 2 Sample T-Tests to test the hypothesis against the population mean for each metric.

Data

Data needed to run the statistical test, could be:
  - Manufacturer (mfg)
  - Engine Size (cyl)
  - Highway Fuel Efficiency (hwy)
  - City Fuel Efficiency (cty)
  - Model Year Cost
