Regularization is a step we can take to prevent overfitting and make our models predict new data better and become more generalized. Regularization itself is when we penalize the model for being too complex and encourage it to become more simpler and general, by making the values for parameters $w_j$ smaller we can cut out the noise. The equation shown below used for regularization for the [[Cost Function]]:

$J(\vec{w},b)=\frac{1}{2m}\sum_{i=1}^{m}(f\vec{w},b(\vec{x}^{(i)})-y^{(i)})^{2}+\frac{\lambda}{2m}\sum_{j=1}^{n}w_{j}^{2}$

Where lambda or $\lambda$ is the regularization parameter we use, although note while we are making the term $\lambda$ to be very small  but is always $\lambda > 0$ (greater than 0). This is because if we make $\lambda = 0$ we would just be eliminating all our features and just leaving our bias of $b$.  We can also include of or exclude the regularization of $b$ but it makes very little difference in practice but it is shown below:

$J(\vec{w},b)=\frac{1}{2m}\sum_{i=1}^{m}(f\vec{w},b(\vec{x}^{(i)})-y^{(i)})^{2}+\frac{\lambda}{2m}\sum_{j=1}^{n}w_{j}^{2}+\frac{\lambda}{2m}b^{2}$

Regularization for gradient descent for linear regression looks similar and is shown below:

Equation for regularized linear regression

$J(\vec{w},b)=[\frac{1}{2m}\sum_{i=1}^{m}(f\vec{w},b(\vec{x}{(i)})-y^{(i)})^{2}+\frac{\lambda}{2m}\sum_{j=1}^{n}w_{j}^{2}]$

Equation for gradient descent

repeat {

$w_j = w_j - \alpha\frac{d}{dw_{j}}J(\vec{w},b)$
$b = b - \alpha\frac{d}{db}J(\vec{w},b)$

}

Now if we substitute our equation for regularized linear regression into our equation for gradient descent we get:

repeat {

$w_j = w_j - \alpha[\frac{1}{m}\sum_{i=1}^{m}[(f\vec{w},b(\vec{x}^{(i)})-y^{(i)})x_{j}^{(i)}]+\frac{\lambda}{m}w_{j}]$
$b = b - \alpha\frac{1}{m}\sum_{i=1}^{m}(f\vec{w},b(\vec{x}^{(i)})-y^{(i)})$

}

Note we haven't regularized $b$ because it isn't necessary to do it.

Now for the regularized for the Logistic Cost Function and logistic regression is shown below:

$J(\vec{w},b) = -\frac{1}{m}\sum_{i=1}^{m}[y^{(i)}log(f\vec{w},b(\vec{x}^{(i)}))+(1-y^{(i)})log(1-f\vec{w},b(\vec{x}^{(i)}))]+\frac{\lambda}{2m}\sum_{j=1}^{n}w_{j}^{2}$

Equation for gradient descent

repeat {

$w_j = w_j - \alpha\frac{d}{dw_{j}}J(\vec{w},b)$
$b = b - \alpha\frac{d}{db}J(\vec{w},b)$

}

Now if we substitute our equation for  logistic regression into our equation for gradient descent we get:

repeat {

$w_j = w_j - \alpha\frac{1}{m}\sum_{i=1}^{m}\frac{1}{1+e^{-(\vec{w}\cdot\vec{x}+b)}}+\frac{\lambda}{m}w_{j}$
$b=b-\alpha\frac{1}{m}\sum_{i=1}^{m}\frac{1}{1+e^{-(\vec{w}\cdot\vec{x}+b)}}$

}
