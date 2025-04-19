Linear regression is just a machine learning algorithm which tries to predict data by trying to draw the line of best fit. It uses training set which comes with "x" and "y", also known as features and labels then creates a model based. This allows us to predict for an "x" which is not on the data set.

In simple terms we can think it basically as the equation of a straight line which is $y = mx + b$ but in machine learning we use slightly different terms which is $y' = b + w_1 x_1$.

Where:

- $y'$ is the predicted label otherwise known as the output
- $b$ is bias for the model and would be known as the y-intercept. Note: Sometimes $b$ is referred to $w_0$ 
- $w_1$ is the weight of the feature and would be know as the slope
- $x_1$ is the feature of the model or known as the input

![[Pasted image 20250418201542.png]]

While the above example only shows one feature in the real world machine learning model often need and have multiple features. For example measuring the mileage of a car, a simple model might only include the weight of the car for a feature, but a more sophisticated model will have additional features which would look something like:

$y' = b + w_1x_1 + w_2x_2 + w_3x_3 + w_4x_4 + w_5x_5 +  ... + w_nx_n$  

Where:
- $w_1$ would represent weight in pounds
- $w_2$ would be displacement
- $w_3$ would be acceleration
- $w_4$ would be number of cylinders
- $w_5$ being horsepower
- $w_nx_n$ being any additional features and weights

When we train model we update values for $b$ and $w$ to find a model which best fits our data.

We can rewrite the equation above to simplify as shown below:

$y' = \vec{w}\cdot \vec{x} + b$

$\vec{w}$ is equal to all the row vector of all the weights and $\vec{x}$ is equal to all the row vector of all of features as shown below:

$\vec{w} = [w_1  w_2  w_3  ...  w_n]$
$\vec{x} = [x_1 x_2 x_3 ... x_n]$

Then we calculate the dot product $\cdot$ of all the weights and features and combine them. This is know as Multiple Linear Regression.

![[Pasted image 20250419174432.png]]

When coding for this we can use the library called NumPy to speed up our calculation so it runs more efficiently due to vectorization. Once we import the library we can you the code `f = np.dot(w,x) + b` so instead writing a for-loop to go through each row vector or manually writing it it will be more computationally efficient. As stated before, when running through a loop it takes the computer multiple steps to go through all the iterations of the training data one by one, but when implementing NumPy we can user parallel computing so it computes the dot product in one step as shown below.

![[Pasted image 20250419181158.png]]


%% The following below is based upon Stanford's Supervised Machine Learning: Regression and Classification, update it to include Loss functions from [Google ML Crash Course](https://developers.google.com/machine-learning/crash-course/linear-regression/loss)%%

We can use the [[Cost Function]] (also sometimes interchanged with the loss function) which allows us to adjust our linear regression model so it more accurately predicts data. This is done my comparing the predicted data vs the actual data. Usually we try to minimize the cost function in most areas because it means our model is accurate as it has good predictions.  

Another algorithm we use is [[Gradient Descent]] it is an optimization algorithm which tries to find the best weights and bias for linear regression by finding the lowest cost function. It works but calculating the current cost function, and attempts to move in the direction which will reduce its cost function the most for that instance, and then changing the weights and biases reflection that.  It then repeats this process until it finds the lowest cost function available and reduce it any further.