Logistic regression is a [[Supervised Learning]] algorithm which is used for classification where we have to predict the probability of an output between 0 and 1 given an input. We can then take the output of that function and either take it as an applied "as is", meaning if in a spam-prediction model the output value is 0.932, it would imply a 93.2% probability that the email is spam. Otherwise we can convert it into a binary category such as, True or False, Spam or Not Spam.  

We use the Sigmoid function (also known as logistic function, and creates an "s shape") to calculate the probability in logistic regression, which ensures the output of a given model, is between the value of 0 and 1. The formula for the sigmoid function is shown below:

$f(x) = \frac{1}{1+e^{-x}}$

![[Pasted image 20250420183830.png]]

As the value of $x$ increases, our value $f(x)$ gets closer and closer to the value of 1 but never fully reaches it. As the value of $x$ decreases, $f(x)$ gets closer and closer to 0 but again never fully reaches it.

If we have a linear regression model and we want to transform it into an sigmoid function we can use the following equation 

Given the linear model is $f\vec{w},b(\vec{X}) = \vec{w} \cdot \vec{x} + b$

Where we would make $z = \vec{w} \cdot \vec{x} + b$

And plug it into the logistic regression mode of $y' = \frac{1}{1+e^{-z}}$

Which would give $y' = \frac{1}{1+e^{-(\vec{w}\cdot\vec{x}+b)}}$

%% I know I used different values for output and input and its a little confusing but its easier for me to understand
 %%

The decision boundary is the the cutoff for whether the output of the model is either 1 or 0. We can find the decision boundary of an model by calculating for z = 0. As shown below
![[Pasted image 20250420191734.png]]

We can also do non-linear logistic regression, where again we would make z = 0 and it will help us find the decision boundary again shown below.

![[Pasted image 20250420192106.png]]
You can get very complex boundaries when using non-linear models which would accurately fit the data, and improve the accuracy of the model. 

To measure the error of the sigmoid function, we can't use the same function we used for linear regression because in linear regression we had values for $y'$ which range from all real numbers. But since we are doing classification, we can only have values for $y'$ ranging from 0 to 1.

We can use the [[Logistic loss function]], also known as the log loss function which will help us calculate the given error and help us correct our model for when we use it in the Cost function for logistic regression and do gradient descent for logistic regression.

When doing [[Gradient Descent]] for logistic regression it will use the same concepts as we learned for the linear regression. We will monitor the learning curve and see when it plateaus, do an vectorized implementation so when we code it becomes more efficient and requires less compute, and we will also scale features as needed. 

When creating models it is also possible for model to either [Overfit](obsidian://open?vault=Obsidian%20Vault&file=Machine%20Learning%20Specialization%2FOverfitting) or Underfit the data. When the model matches the training data very closely with 0 or almost no errors it would mean our model will fail to make predictions given new data and it has an high variance. Alternatively, when you underfit a model it will make poor predictions because the model hasn't taken account of the complexity of the training data otherwise known as having a high bias. 

![[Pasted image 20250421165702.png]]

The image above shows when the model has underfit, and over fit the data, as well as when it has generalized that data well.

