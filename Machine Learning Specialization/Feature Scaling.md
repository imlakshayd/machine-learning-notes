Feature scaling is used to standardize the features of an model so they are relative to each other. We do this at the data pre-processing level so our model correctly handles different values correctly. While feature scaling is not required all the time it can speed up the process of convergence on gradient descent, which leads it to be more efficient. 

For example, if we have an model to predict housing prices and our features are $x_1$ : size ($feet^2$) which has a range from 300 - 2000 square feet and $x_2$ : number of bedrooms which has a range of 1-5. Due to the fact that the features are not on scale with each other it would lead to the model to slowly and inefficiently reach convergence. We can solve this by translating and scaling the feature so both $x_1, x_2$ have the range from 0-1. This will allow gradient descent to be more efficient and lead to a convergence at a more ideal outcome and less skewed outcomes, as the algorithms tend to user greater values as higher and consider smaller values as lower regardless of the unit of the value.

It should also be noted that parameter size also matters. For example, if $w_1$ has a value of 50 (thousands of dollars) and $w_2$ has the value of .01 and we have b = 50. Using the regression formula it would look like this:

Actual price of house is 500k
$x_1$ : size ($feet^2$) = 2000 sq ft
$x_2$ : number of bedrooms = 5 bedrooms
$w_1$ = 50
$w_2$ = 0.1

$y' = w_1 x_1 + w_2 x_2$
$y' = (50)(2000) + (0.1)(5)$
$y' = 100,000,000$

The predicted price of the house would be $100 million dollars, this is due to parameters are not set to right values, in general if the feature is large we use a smaller parameter value, and if the feature is small we use a bigger parameter.

![[Pasted image 20250419233200.png]]

If we recalculate with different parameter values we would get:

 Actual price of house is 500k
$x_1$ : size ($feet^2$) = 2000 sq ft
$x_2$ : number of bedrooms = 5 bedrooms
$w_1$ = 0.1
$w_2$ = 50

$y' = w_1 x_1 + w_2 x_2$
$y' = (0.1)(2000) + (50)(5)$
$y' = 500,000$

We get $500,000 which matches the actual price of the house.

We have multiple ways to scale features one of the include the **Min Max scaling**. We scale the features in the range 0 to 1 and we can do this simply by dividing the iteration by the maximum value. For example, lets say our range for $x_1$ is between 300 to 2000 sqaure ft and our range for $x_2$ is between 0 to 5 the scaled range would be:

$x_{1,scaled} = \frac{x_{1}}{x_{1, max}}$

$x_{2,scaled} = \frac{x_{2}}{x_{2, max}}$

$x_{1}$ scaled min value $= \frac{min}{max}$

which gives us the new ranges of 

$0.15 \le x_{1,scaled} \le 1$ and $0 \le x_{2,scaled} \le 1$

Another method to scale features is through **normalization** which puts the values usually between the ranges of -1 to 1 and is similar to the min-max scaling. We subtract the average (also know as Mu or $\mu$) of the feature from the iteration of x and divide it by the max subtracted by the min values. It formula looks like the following below:

$x_1$ normalized $= \frac{x_1-\mu_{1}}{max-min}$ 

$x_2$ normalized $= \frac{x_2-\mu_{2}}{max-min}$ 

which would give the ranges of

$-0.18 \le x_1 \le 0.82$ and $-0.46 \le x_2 \le 0.54$

**Standardization** also known as **Z-Score Normalization** is another way to scale features by subtracting the mean and dividing it by the standard deviation (also known as Sigma or $\sigma$). Standard deviation is the variance from the mean. 
![[Pasted image 20250420001548.png]]

The formula for Z-score normalization is shown below as the following:

$x_1 = \frac{x_1 - \mu_{1}}{\sigma_1}$

$x_2 = \frac{x_2 - \mu_{2}}{\sigma_2}$

which would give the ranges of

$-0.67 \le x_1 \le 3.1$ and $-1.6 \le x_2 \le 1.9$

The image below shows how our plotted data would look like compared to after we normalize it or standardize it.

![[Pasted image 20250420002737.png]]

We generally want our features to be between the ranges of $-1 \le x_j \le 1$ for each feature $x_j$ the table below shows when rescaling is necessary or not given the range .

| Range               | Evaluation   | Action       |
| ------------------- | ------------ | ------------ |
| 0 ≤ x₁ ≤ 3          | Within range | No rescaling |
| -2 ≤ x₂ ≤ 0.5       | Within range | No rescaling |
| -100 ≤ x₃ ≤ 100     | Too large    | Rescale      |
| -0.001 ≤ x₄ ≤ 0.001 | Too small    | Rescale      |
| 98.6 ≤ x₅ ≤ 105     | Too large    | Rescale      |

