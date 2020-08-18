# House-Prices: Advannced Regression Techniques

# Problem Description


Ask a home buyer to describe their dream house, and they probably won't begin with the height of the basement ceiling or the proximity to an east-west railroad. But this playground competition's dataset proves that much more influences price negotiations than the number of bedrooms or a white-picket fence.
With 79 explanatory variables describing (almost) every aspect of residential homes in Ames, Iowa, this competition challenges you to predict the final price of each home.


# Missing Value Treatment
Data in real world are rarely clean and homogeneous. Typically this is because of the following reasons:

1. Corrupt data

2. Failure to load information

3. Incomplete extraction

4. Noisy, and inconsistent

5. Incomplete data

So it is an important task of a Data scientist to prepossess the data by filling missing values because making the right decision on how to handle it generates robust data models. It is important to be handled as they could lead to wrong prediction or classification for any given model being used. The goal of this article is to cover the basic techniques for handling missing values in a data set.

Real-world data often has missing values.

Firstly we cannot simply ignore missing values in a data set. We must handle them in some way for the very practical reason that most algorithms do not accept missing values.

"Common sense" is not sensible here.From my experience the 2 most commonly recommended ways of dealing with missing data actually are not accurate .

They are:

1. Dropping observations that have missing values

2. Imputing the missing values based on other observations

3. Dropping missing values is sub-optimal because when we drop observations, we drop information.

The fact that the value was missing may be informative in itself.We need to understand business deeper to uncover why this information is missing in real world problems.In real time problems we need to make predictions even if some of the features are missing !!!.

Imputing missing values is sub-optimal because the value was originally missing but you filled it in, which always leads to a loss in information, no matter how sophisticated our imputation method is.

"Missingness" is almost always informative in itself, and we should tell our algorithm if a value was missing.Even if we build a model to impute our values, we are not adding any real information. You’re just reinforcing the patterns already provided by other features.

Missing numeric data
1. For missing numeric data, we should flag and fill the values.

2. Flag the observation with an indicator variable of missingness.

Secondly fill the original missing value with 0 just to meet the technical requirement of no missing values.

By using this technique of flagging and filling, we are essentially allowing the algorithm to estimate the optimal constant for missingness, instead of just filling it in with the mean.

Missing categorical data
The best way to handle missing data for categorical features is to simply label them as ’Missing’!

We are essentially adding a new class for the feature.

This tells the algorithm that the value was missing.

This also gets around the technical requirement for no missing values.

Missing values Treatment Techniques

1.Deleting Data

This method is the most commonly used to handle the null values. Here, we either delete a particular record if it has a null value for a particular feature ,and a particular feature if it has more than 70-75% of missing values. This method is advised only when there are enough samples in the data set.

Note : One has to make sure that after we have deleted the data, there is no addition of bias. Removing the data will lead to loss of information which will not give the expected results while predicting the output.

Imagine we drop one whole observation just because one of the features had a missing value, even if the rest of the features are perfectly filled and informative!

2. Back-fill or Forward-fill

Back-fill or forward-fill to propagate next or previous values respectively.

3. Replace with constant value

Replace with some constant value outside fixed value range-999,-1 etc This method is useful as it gives the possibility to group missing values as a separate category represented by a constant value. It is a preferred option when it doesn’t make sense to try and predict a missing value. The downside is that performance of linear models can suffer.Use a global constant to fill in for missing values. For example, in the titanic data set filling in the missing value of the Embarked feature with the most common Port of Embarkation might not really makes sense as opposed to using something like “N/A”.

4. Replacing With Mean/Median/Mode

This strategy can be applied on a feature which has numeric data like the age of a person or the ticket fare. We can calculate the mean, median or mode of the feature and replace it with the missing values. This is an approximation which can add variance to the data set. But the loss of the data can be negated by this method which yields better results compared to removal of rows and columns.

5. Assigning An Unique Category

A categorical feature will have a definite number of possibilities, such as gender, for example. Since they have a definite number of classes, we can assign another class for the missing values. When some of the features have missing values they can be replaced with a new category, say, U for ‘unknown’. This strategy will add more information into the data set which will result in the change of variance. Since they are categorical, we need to find one hot encoding to convert it to a numeric form for the algorithm to understand it.







© copyright 2020 Saptarshi Datta - All Rights Reserved
