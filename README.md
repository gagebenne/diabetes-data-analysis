# Diabetes Analysis
*Gage Benne*

## Introduction

According to the [CDC](https://www.cdc.gov/diabetes/pdfs/data/statistics/national-diabetes-statistics-report.pdf), around 2.8% of individuals living in the United States that have undiagnosed diabetes. Early discovery and diagnosis are key to preventing and managing diabetes.

We will explore a dataset courtesy of Dr. John Schorling at the Department of Medicine, University of Virginia School of Medicine. This dataset consists of was conducted to understand the prevalence of obesity, diabetes, and other cardiovascular risk factors amongst African Americans in central Virginia.

The dataset consists of 19 health-related variables, with our target variable being `glyhb` or [glycosylated hemoglobin](https://en.wikipedia.org/wiki/Glycated_hemoglobin). This is a diagnostic test often referred to as simply a "hemoglobin A1c", is measured primarily to determine the three-month average blood sugar level. Often this metric is used to diagnose individuals with diabetes. Using the [CDC](https://www.cdc.gov/diabetes/managing/managing-blood-sugar/a1c.html) for reference, a normal A1c level is anything below 5.7%. Prediabetics would have A1cs between 5.7 - 6.4%, and those individuals with a level of 6.5% or more indicates diabetes.

### [Ask](ask.md)

Our primary goal is to predict the diagnosis of diabetes using a subset of the variables in the dataset. We elaborate on this step using the CoNVO framework:

- **Co**ntext - what is the context?
- **N**eed - what organizational need requires fixing?
- **V**ision - what is required and what does success look like?
- **O**utcome - how will the result work itself back into the organization?

Picking an appropriate problem and setting expectations correctly will guide the analysis and our modeling.

### [Get](get.ipynb)

The dataset generiously provided courtesy of the Vanderbilt University Department of Biostatistics is collected using their [datastore](https://hbiostat.org/data/#vanderbilt-biostatistics-datasets). The dataset is cleaned relevant to domain knowledge and the question being proposed. Once this is done, the cleaned data is saved in a flat file format: [cleaned-diabetes.csv](cleaned-diabetes.csv).

### [Explore](explore.ipynb)

With the interesting question posed, and the dataset collected, we attempt to gain a deeper level of understanding of our dataset by performing structured exploratory data analysis. Using visualizations, we explore first the single variables, then pairwise relationships guided by domain knowledge and the overall question. Due to the combinatorial explosion of our dataset's 19 variables, we limit the pairwise exploration to relationships relevant to the question being asked.

At times interesting relationships and additional data transformations are discovered during this step, so an additional data set -- [explored-diabetes.csv](explored-diabetes.csv) -- is produced. These are any modifications or transformations that might've occured during exploratory data analysis that might be interested during model exploration.

### [Model](model.ipynb)

Informed by our exporative data analysis, we embark on the model-building journey. We perform various data transformation and exclusions to optimize a linear regression model. This model uses variables from the dataset to predict hemoglobin A1c (`glyhb`). Once the model is refined and validated, we analyze its performance (especially compared to a null model where our prediction is the mean). We utilize the model to predict two fictitious individuals, as well as construct a classification model using the linear regression model. We calculate model accuracy by determining the percentage of accurate diagnosis of all the individuals in the dataset based on the model prediction.

### [Report](report.pdf)

Lastly, we summarize and reflect on the findings of the process. This includes conclusions we found during our data exploration, as well as data modeling. Results pertaining to the overall objective of the question being asked are also discussed.
