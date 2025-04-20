Feature engineering is when we create new features or combine and transform existing features to improve the machine learning model's performance by using intuition to get relevant information for the model.  

![[Pasted image 20250420165814.png]]

For example, lets say we have a model for predicting house prices and the features we choose are $x_1$ for the size of the frontage of the house and $x_2$ for the depth of the house. 

$f\vec{w},b(\vec{x})=w_1 x_1 + w_2 x_2 + b$

We can actually use the frontage and the depth to get the area of the house, which we can describe as an entirely new feature, as $x_3 = x_1 x_2$. Our new model will look like

$f\vec{w},b(\vec{x})=w_1 x_1 + w_2 x_2 + w_3 x_3 + b$

Where:
$x_1 = frontage$
$x_2 = depth$
$x_3 = area$

