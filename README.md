# BayesianPrimer

This is a tutorial notebook on how to approach a problem using Bayesian statistics. The notebook aims to answer a question similar to "What is Phil's height?" by applying Bayesian inference to estimate the mean of a sample based on observed data.

## Conceptual Overview

### Bayesian Inference
Bayesian inference is a statistical method that updates the probability of a hypothesis as more evidence or information becomes available. It combines prior beliefs (prior distribution) with the likelihood of observed data to form a posterior distribution, which represents the updated belief after considering the evidence.

### Prior Distribution
The prior distribution reflects our initial beliefs about the parameter before observing any data. In this notebook, we assume Phil's height follows a normal distribution with a mean (`mean_height`) of 182 cm and a standard deviation (`std_dev`) of 12.7 cm. This is represented mathematically as:

$$ \text{prior\_pdf}(x) = \frac{1}{\sigma \sqrt{2 \pi}} \exp\left( -\frac{1}{2} \left( \frac{x - \mu}{\sigma} \right)^2 \right) $$
where \(\mu = 182\) and \(\sigma = 12.7\).

### Likelihood Function
The likelihood function represents the probability of the observed data given a specific value of the parameter (in this case, Phil's height). Given measurements with a known uncertainty (standard deviation of 5 cm), the likelihood for each measurement is calculated as:

$ \text{likelihood}(measurement, \theta) = \frac{1}{\sigma \sqrt{2 \pi}} \exp\left( -\frac{1}{2} \left( \frac{measurement - \theta}{\sigma} \right)^2 \right) $

where $\sigma = 5$.

### Posterior Distribution
The posterior distribution combines the prior distribution and the likelihood of the observed data to provide an updated belief about the parameter. It is calculated as:

$ \text{posterior\_pdf}(\theta) \propto \text{prior\_pdf}(\theta) \times \text{likelihood}(\text{data}, \theta) $

The posterior is then normalized so that the area under the curve equals 1.

### Implementation
1. **Prior PDF Function**: Defines the prior probability density function based on the assumed normal distribution of Phil's height.
2. **Likelihood Function**: Calculates the likelihood of the observed measurements for different values of Phil's height.
3. **Posterior PDF Function**: Combines the prior and likelihood to compute the posterior distribution.

### Visualization
The notebook overlays the following curves:
1. **Prior Distribution**: Our initial belief about Phil's height.
2. **Likelihood of Each Data Point**: Individual likelihood curves for each measurement.
3. **Joint Likelihood**: Combined likelihood of observing all measurements.
4. **Posterior Distribution**: The updated belief about Phil's height after considering the observed data.

## To View the Notebook
[Click here!](https://nbviewer.org/github/emcarthur123/BayesianPrimer/blob/main/first_posterior_PDF.ipynb)

