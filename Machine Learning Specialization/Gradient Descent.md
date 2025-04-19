Gradient Descent is used within [[Linear regression]] by continuing to adjust the weights and bias of the cost function and optimizing it for the least loss. It starts with its given cost function and from there on it looks to move in the direction which would minimize the loss the greatest. It continues to iterate this until it comes to the lowest loss for the function at which point it can't go any further.

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

The learning is a positive value which is chosen by you when doing Gradient descent, although we a want learning rate to be not too small or big. If the learning rate is too big it can overshoot and never reach the minimum and can fail too converge to it. While if the learning rate is too small it might take too many steps and too much time which can slow our algorithm down. Also note that when gradient descent is closer and closer to the minimum it will take smaller and smaller steps automatically because the derivative itself becomes smaller.

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
 