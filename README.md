# Car Price EDA and Prediction
## About the Data
The data used in this analysis was taken from the following data source: <a href="https://archive.ics.uci.edu/ml/machine-learning-databases/autos/imports-85.data" target="_blank">https://archive.ics.uci.edu/ml/machine-learning-databases/autos/imports-85.data</a>
The dataset contains <b>201 observations</b> and <b>28 columns</b>.
## Methodology
Exploratory data analysis was performed on the dataset including cleaning, enriching and transformation of data. Correlation analysis was conducted along with appropriate statistical significance calculations based on which the features imperative to the price prediction model were determined.
![Image1](imgs/correlation_heatmap.PNG)
![Image2](imgs/pairplot.PNG)
Firstly, a simple linear regression model was developed using only <b>horsepower</b> as a feature. The following diagram depicts the result obtained from the model compared to the actual data points.
![Image3](imgs/slr.PNG)
The mean cross-validation score obtained by using 5 folds with the data was $0.5220592359225417 $. This model was slightly improved upon by using multiple linear regression.
![Image4](imgs/mlr-train.PNG)
Mean cross-validation score for this model was calculated as $0.5465033840125946$,  a slight improvement from the previous simple linear regression model. Subesequently a simple linear regression model with polynomial features, experimenting with degrees was developed.
![Image5](imgs/plr-deg5.PNG)
Above is the figure for polynomial regression with  a degree of 5, using only horsepower as the feature. After this, a multiple linear regression with polynomial features model was developed (degree=2).
![Image6](imgs/mplr-deg2.PNG)
This model was a further improvement, obtaining an $R^2$ value of $0.6044870441643057$ on the test data. A ridge regression model with varying models of alpha hyperparameter was developed in the following section.
![Image7](imgs/R2valuealpha.PNG)
The above diagram shows the $R^2$ scores as they vary with $\alpha$, it was noticed that as alpha increased, $R^2$ value fot the validation data increased upto a point after which it decreased and saturated. The $R^2$ value on the training data showed a reverse trend, it decreased with an increase in alpha. This is a demonstration of the bias-variance tradeoff: as the model is made more more general, it loses it specificity to the training data. <br>
Finally, grid seach was employed on the ridge regression model to find the optimal value for hyperparameter $\alpha$.
![Image](imgs/gridsearch.PNG)
This model obtained a mean cross validation score of of $0.9376433845014158
$. Finally we have arrived at a reasonably accurate predictor of price for the automobile data given.
## Tools and Techonologies used
<ul>
<li><b>Techonologies</b>: Jupyter Notebook, Python
<li><b>Libraries</b>: Pandas, scikit-learn, SeaBorn, MatPlotLib, numpy, scipy, ipywidgets, tqdm
</ul>
