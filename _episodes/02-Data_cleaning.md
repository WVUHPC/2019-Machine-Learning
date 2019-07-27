---
title: "Data Cleaning, Imputation, Cross-Validation"
teaching: 10
exercises: 0
questions:
- "Key question (FIXME)"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---


We will spend most of our time on selecting and cleaning the data which will be used for our machine learning. If the data is not treated correctly, the results can be misleading. Therefore, if the data is not very clean and we use a specific machine learning algorithm, it will be like injecting a virus into the system. Bad data can lead to the famous GIGO phenomena, Garbage in, Garbage out.


Therefore, it will be nice to have a strategy on how to deal with data in general:

1) Data Quality. This concept is really field dependent. I won't be able to offer a very general definition but at least I will try to offer some boundaries. 

The data needs to define the rules or contraints present in the problem and provided as columns per each property with an entry per data. 

For example, the data needs to have specific assignation, being integer, boolean, a date, etc. Besides, these data can also have some range that could be known in advance, for example 
dates are bounded or the existence of tipical numbers, etc. As the data is provided, some of the columns can be empty but also some others should be filled out, knowing in advance that can improve 
the data analysis. Each column or a subset of columns need to be unique across the dataset but having the same data fields for each entry. There are also some defined pattern that could be 
present in the data, for example the number of digits of the bank account or the possible bill types available. Lastly, some of the data can be cross-field validates, 
as for example values could not exist if some other data is available. For example the user should not have any money in the account unless the account has been already created.


We need also to check that the available data is as genuine as possible. Even after all the previous checks have passed, we need to find if the provided data is realistic, for example that a bank account has the basic rules for the possible digits from the bank. We also need to check that the provided information is precise, as for example that addressed are as accurate as possible or that phone numbers really exist. 


Besides the accuracy and validity of the data, it is important that we are aware of missing data. This is a fact that frequently happen and it can be mitigated by rechecking the data and filling the missing info or increasing the boundaries to allow unknown data to exist as a possible outcome.


Another important data feature is the so called consistency between the data set or in the case of multiple data sets. For example having 20 trillion in an account from a US citizen in an African bank. We do not know if the number is correct as it can be due to different exchange ratio or can be due to the bank type. This cross comparison are also important to clean the data. This leads also to the data uniformity. Data needs to be checked with respect to the used units, which means that a universal set of units needs to be used within the data.


2) The workflow. Here we now describe the methodology that we advise to follow to accomplish the explained data criteria.


    a) Inspection. This is probably the most time comsuming part. First of all, we need to perform some data statistics (data profiling) to get an idea of the quality of the data (dispersion, variability, etc) . Completnes of the data set and account for missing values.  At this stage it would be very useful to visualize the data and perform a statistical analysis such as the average, the quantile, the standard deviation, etc. This information can give us ideas on possible erroneous or unexpected data.

    b) Cleaning: Fix or remove the anomalies discovered. We can also try to bound the data based on the "useness" of the different fields and throwing everything that is irrelevant. Another important check is to find duplicates, as they can be present in the data without knowing it. There is software that allows data (pandas in Python is a good package). Check data conversion and avoid different scales between data. Syntaxis errors can be also easly spotted. For example stripping space at the beginning and end of strings as well as adding padding to constraint digits or words to have the same length. At the same time, you can also correct for typos, as it is typical that in entries small mispellings are present and depends on the data classification (easily done by using dictionaries or pattern match in Python). A more tricky method would be to use the so called fuzzy matching, which is a method that calculates the distance between strings (counting the number of operations needed to convert one string into the other).

Finally, in the data we need to standardized the format of the provided data (all strings in lower or upper case, numerical values wiht the same unit, etc). This can required to apply some data scaling to transform the data to have a specific scale (all numbers between 1-1000 for example) or depending on the data, you can also use functions that reduce the skewness of the data such as the log or the inverse function. As we look into the data distribution, it will be also possible to normalize the data, as it becomes more maneagable. 

One important factor that you will also have to face is that in many cases, data is missing. In that case, there are three options that you need to explore.  If the values are very scarce or they seems random, it will be easier to drop all observations. This can be concluded by using some type of statistical analysis.  If a value seems to be off, you can drop it if the datafile is not large enough but also you can impute it. For that, an statistical analysis can help you with that, for example by seeing if the distribution is or is not skewed or if it is normally distributed. If a correlation between the column where the missing datawith a different column is noticed, you can use regression or K nearest neighbor methods to predict data that is off (some discussed later).  A last resource could be that other data can be used to fill the missing data. This last technique can be also dangerous, therefore, we do expect that you use it only in case you have enough data. In case that none of the previous methods help in defining the missing data, you should flag those and keep those away from any statistical analysis for those specific columns. 

We should stress that within the proposed procedure, you can find data that is really off but it does not necessarily mean that they are wrong. Those are called outliers and we should start by trusting the existence unless we prove that they are wrongly obtained. The existence of that data could be of great relevance but because of that, we need to recheck that this data is really Ok. For example checking correlation with other data or applying of any possible constraint. It is important to now that given the fact that outliers are very uncommon, machine learning methods have a tuff time predicting their existence. 



    c) Verifying: After the large process of data cleaning, we need to inspect how healthy is the data. For example, if there are error bars associated with the used data or if the data has been obtained safetly. Therefore, this process is very tighted with the cleaning process performed previously.


Reporting how healthy the data is, is equally important to cleaning.

As mentioned before, software packages or libraries can generate reports of the changes made, which rules were violated, and how many times.

In addition to logging the violations, the causes of these errors should be considered. Why did they happen in the first place?.


    d) Reporting: it is very important that we create a transparent method to report the status of the database. There is software the allows to report the data status, for example of the impossed constraints, how may times those were violated or it there are suspicious data, it can also point out the frequency of those. A good analysis of the database is one of the most important keys for machine learning prediction.



{% include links.md %}
