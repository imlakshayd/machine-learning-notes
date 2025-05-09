Gradient Descent is used within [[Linear regression]] and [[Logistic regression]] by continuing to adjust the weights and bias of the cost function and optimizing it for the least loss. It starts with its given cost function and from there on it looks to move in the direction which would minimize the loss the greatest. It continues to iterate this until it comes to the lowest loss for the function at which point it can't go any further.

![[Pasted image 20250418181637.png]]

In the image above we are trying to get the man down the hill in the fastest way possible. The red circles below his feet represent two different starting points (cost functions). You can see how with every step the man takes it tries to descent the hill (gradient) by doing down the steepest way. Even though the starting points are only slightly different the fastest way to get down for the man changes as he tries to take the steepest step each time, which eventually leads him to the bottom of the hill, but at too different points.

Below is the mathematical representation of Gradient descent: 

![[Pasted image 20250418183453.png]]

Where:
- $w$ is the weight 
- $b$ is the bias 
- $\alpha$ known as alpha or the learning rate
- $\frac {d}{dw}  J(w,b)$ is the derivative of the cost function for the weight
- $\frac {d}{db}  J(w,b)$ is the derivative of the cost function for the weight

We should update the algorithm simultaneously meaning not first updating for $w$  or $b$ and substituting the values but doing it at the same time and then substituting them into the new cost function

![[Pasted image 20250418184337.png]]

![[Pasted image 20250418184354.png]]

The learning is a positive value which is chosen by you when doing Gradient descent, although we a want [[Learning Rate]] to be not too small or big. If the learning rate is too big it can overshoot and never reach the minimum and can fail too converge to it. While if the learning rate is too small it might take too many steps and too much time which can slow our algorithm down. Also note that when gradient descent is closer and closer to the minimum it will take smaller and smaller steps automatically because the derivative itself becomes smaller.

Our previous notation of Gradient descent was not vectorized and only dealt with one feature and weight, while in the real world we can have multiple features and weigh. Below is the formula which is the vectorized form using multiple features and weights for $n$ features $(n \ge 2)$:

repeat {

$w_1 = w_1 - \alpha \frac{1}{m} \sum_{i=1}^{m} (f\vec{w},b)(\vec{x}^{(i)})-y^{(i)})x_{1}^{(i)}$

Note that $\frac{1}{m} \sum_{i=1}^{m} (f\vec{w},b)(\vec{x}^{(i)})-y^{(i)})x_{1}^{(i)}$ is just taking the derivative and can be written as $\frac{d}{dw_{1}}J(\vec{w},b)$

Since we have multiple parameters we will update $J$ according until $J=n$ and calculate for all of them as shown below:

$w_n = w_n - \alpha \frac{1}{m} \sum_{i=1}^{m} (f\vec{w},b)(\vec{x}^{(i)})-y^{(i)})x_{n}^{(i)}$

$b=b-\alpha\frac{1}{m}\sum_{i=1}^{m}(f\vec{w},b(\vec{x}^{(i)})-y^{(i)})$

And we will also simultaneously update $w_{j}$ (for  $j =1,...,n)$ and $b$

}

There is alternative to gradient descent called the **normal equation** it only works for linear regression and can solve for w, b without going through iterations, but it is slow when there is a large amount (> 10,000) features. It maybe used in some older libraries in machine learning to implement linear regression, but most of the times we will gradient descent using the equations above for finding w and b.

When doing Gradient descent it is crucial that all the features we use are on a similar scale to one and another. This is called [[Feature Scaling]], if features are not on scale and very different, gradient descent can become inefficient and slow convergence or have erratic updates.

To make sure that gradient descent is working correct would need to look at the [[Learning Rate]] as talked about before and the learning curve. To simply put it we want to minimize our cost function after each iteration and we will know when it close to converge but seeing if the learning curve is starting to plateau. 

What features we use for our model also make a huge impact on how the model will performance and can drastically change it to better predict data. We can choose better features for model or do [[Feature Engineering]] which can allow use to create, transform and combine existing features into new ones which help our model become more accurate.

We might also have features which might not fit the data using just linear regression and we may have a quadratic or cubic model which fits out data better. In that case we can do [[Polynomial regression]]. This allows our features to better fit that data of our model and allows for a more accurate model as well, but when using polynomial regression we should refer back to [[Feature Scaling]] as there ranges are vastly different and it can cause our model to become more efficient.
![[Pasted image 20250420170914.png]]

For [[Logistic regression]] we will use the same concepts as we have applied above for linear regression, but we will instead change the equation we substitute for our model. As shown below

repeat {

$w_j = w_j-\alpha\frac{d}{dw_{j}}J(\vec{w},b)$

$b = b-\alpha\frac{d}{db}J(\vec{w},b)$

} simultaneous updates

When we expand the derivates we get the equation

repeat {

$w_j = w_j-\alpha[\frac{1}{m}\sum_{i=1}^{m}(f\vec{w},b(\vec{x}^{(i)})-y^{(i)})x_{j}^{(i)}]$

$b = b-\alpha[\frac{1}{m}\sum_{i=1}^{m}(f\vec{w},b(\vec{x}^{(i)})-y^{(i)})]$

} simultaneous updates

Now we can substitute our equation for logistic regression which is $f\vec{w},b(\vec{x})=\frac{1}{1+e^{-(\vec{w}\cdot\vec{x}+b)}}$

repeat {

$w_j = w_j-\alpha[\frac{1}{m}\sum_{i=1}^{m}((\frac{1}{1+e^{-(\vec{w}\cdot\vec{x}+b)}}))-y^{(i)})x_{j}^{(i)}]$

$b = b-\alpha[\frac{1}{m}\sum_{i=1}^{m}((\frac{1}{1+e^{-(\vec{w}\cdot\vec{x}+b)}}))-y^{(i)})]$

} simultaneous updates

