# DataScienceProject - Ski Resort Price Prediction

**Problem Statement**

The client is Big Mountain Resort located in Montana who is seeking a new pricing strategy to establish a competitive price that offsets recent increases in operating costs.

**Project Goal**

We will develop a new pricing strategy for BM by leveraging machine learning models to analyze feature correlations with market prices. This approach will enable us to predict how changes in BM's pricing strategy will impact its market position and revenue. By utilizing a data-driven framework, BM will gain insights into its competitive standing and create projections for the potential effects of pricing adjustments.

**Modeling Scenarios**

We created potential scenarios for BM which included either cutting costs or increasing revenue (from ticket prices). Ticket price is not determined by any set of parameters; the resort is free to set whatever price it likes. However, the resort operates within a market where people pay more for certain facilities, and less for others. Being able to sense **how facilities support a given ticket price is valuable business intelligence.** This is where the utility of our model comes in.

The business has shortlisted some options:

1. Permanently closing down up to 10 of the least used runs. This doesn't impact any other resort statistics.
2. Increase the vertical drop by adding a run to a point 150 feet lower down but requiring the installation of an additional chair lift to bring skiers back up, without additional snow making coverage
3. Same as number 2, but adding 2 acres of snow making cover
4. Increase the longest run by 0.2 mile to boast 3.5 miles length, requiring an additional snow making coverage of 4 acres

The expected number of visitors over the season is 350,000 and, on average, visitors ski for five days. Assume the provided data includes the additional lift that Big Mountain recently installed.

**Modeling**

Two types of models were used: 
1. Linear regression imputed with the median and mean values
2. Random forest model by adding additional classifications.

The random forest model has a lower cross-validation mean absolute error by almost $1. It also exhibits less variability. Verifying performance on the test set produces performance consistent with the cross-validation results.

Best Random Forest Regressor Feature Importance:
![RFFeatureImportance](https://github.com/user-attachments/assets/070c4fc4-e73a-4345-846b-2ce2a085db0e)

**Modeling Analysis** 

_Scenario 1 -_

After modeling all four scenarios, we discovered that BM has flexibility in closing down Runs in order to mitigate operating costs:
![RunsCosts](https://github.com/user-attachments/assets/171b1946-db8f-459e-99f1-af29bafd7f36)

The model says closing one run makes no difference. Closing 2 and 3 successively reduces support for ticket price and so revenue. If Big Mountain closes down 3 runs, it seems they may as well close down 4 or 5 as there's no further loss in ticket price. Increasing the closures down to 6 or more leads to a large drop.

BM has among the highest number of total chairs in the market, and according to our model closing one run would not make a significant impact on market ticket price, this is likely because BM is also on the high end of Total number of runs in the market. As these features are close to an optimal range in which a slight increase or decrease would have little utility, it could be suggested to leadership to explore the cost/benefit ratio first by analyzing the operational cost of these features. The model is based solely on market ticket price, and for that reason it is crucial to calculate the cost of the change in any one feature to make sure it doesn’t outweigh the ROI.

_Scenario 2 & 3 - _

Our model shows increased support for ticket price by **$1.99**; over the season, this could be expected to amount to **$347,4638**

In scenario 2 we are increasing the vertical drop by adding a run to a point 150 feet lower down and requiring the installation of an additional chair lift to bring skiers back up. The model shows that the addition of snow making coverage provided by scenario 3 does not make any difference on support for ticket price. 

**Conclusion**

Based on the analysis, Big Mount Resort should consider increasing the vertical drop by 150 feet. This will involve adding one new run and installing an additional chairlift to support the new infrastructure. This adjustment is projected to allow for a ticket price increase of $1.99, raising the current price from $81.00. As a result, this change could potentially increase revenue substantially. 

Given Big Mountain’s 350,000 annual visitors, the $1.99 ticket increase would result in approximately $700,000 in additional revenue.

As well, our model indicates that BM is able to close up to 4-6 runs each day to save on operation costs. However, given that our dataset contains market research data, we cannot estimate the total cost saving. Exploring the cost/benefit analysis of closing runs with data pertaining to BM's operational expenses is highly reccommended.
 
