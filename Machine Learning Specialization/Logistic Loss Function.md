In linear regression we use the [[Cost Function]] as the loss function. For binary logistic regression the outcome of $y'$ can only be somewhere between 0 and 1. Due to the fact that linear regression the graph forms an convex shape which only has one minimum, but in logistic regression there are many local minimums and if we apply the same gradient descent function, we would get stuck in a local minimum as shown below.
%% There is a difference between Loss and Cost, where Loss just means for one iteration, while Cost applies to the whole dataset but many online sources use them interchangeably  %%
![[Pasted image 20250420222318.png]]

In logistic regression since our goal is to simply make our predictions as close to to 1 when our actual data is 1, we can use the following function below:

For if $y^{(i)}=1$
$L(f\vec{w},b(\vec{x}^{(i)}),y^{(i)}) = -log((f\vec{w},b(\vec{x}^{(i)}),y^{(i)}))$

For if $y^{(i)} = 0$
$L(f\vec{w},b(\vec{x}^{(i)}),y^{(i)})=-log(-1(f\vec{w},b(\vec{x}^{(i)}),y^{(i)}))$

Another simpler way to write it is 

 $LogLoss = \sum_{i=0}^{n}-(y_i \times log(p_i) + (1-y_1) \times log(1-p_1))$

Where:
$n$ is the number of samples
$i$ is the index
$y_i$ is the actual value (whether $y=1$ or $y=0$) for index $i$
$p_i$ is the predicted value

Lets say if :
$y_i = 1$ (Actual value)
$p_i =1$ (Prediction)

Our Log-Loss  for that would be 0 and it would mean our model is working correctly but...

Lets say if:
$y_i = 1$ (Actual value)
$p_i =0$ (Prediction)

Our Log-Loss for that would be approaching $\infty$ 

Now lets say if:
$y_i = 0$ (Actual value)
$p_i = 0$ (Prediction)

Our Log-Loss again would be 0 but...

Lets say if:
$y_i = 0$ (Actual value)
$p_i =1$ (Prediction)

Our Log-Loss for that would be approaching $-\infty$ 

What we can conclude is that when our actual value if 1, the loss will be the lowest when it close our prediction is close to the actual value and the further prediction is from our actual data it will have higher loss.