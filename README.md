# bayesian_analysis_plastic_strength
Bayesian Analysis of the plastic strength when subjected to a variety of temperature and pressure

Bayesian Analysis of the plastic strength when subjected to a variety of temperature and pressure. I developed 2 statistical models for this problem:

- applied linear regression using as features temperature and pressure, and as response variable the necessary strength to break up the plastic
- modelled the relation between temperature and pressure as the Gay-Lussac’s Law, which states that the pressure over the temperature follows a constant. The assumption was made because plastic and subjected to high temperature tends to be malleable, mimicking the liquids.

It seemed to have a linear dependency between the features and the response. So I used linear regression to recover the curve. Once with the coefficients of the linear equation, I defined each coefficient a random variable with Normal distribution with the coefficients of the linear model as the mean of the Normal distribution.

Then I used Gibbs Sampling (JAGS R-package) to approximate the posterior distribution of each parameter.

I validated the models using the mean-squared-error (which is a poor metric in this case), and DIC (Deviance Information Criterion). DIC takes into account the model fit (with MSE) but penalizing the complex models (with many parameters). Complex models tends to overfit the data.
