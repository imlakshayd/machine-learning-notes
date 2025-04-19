The cost functions is used within [[Linear regression]] to measure how well the model's prediction aligns with actual data. Using the actual and predicted data we can calculate the difference and adjust the weights and parameters of the model.

The cost function uses the [[Mean Squared Error]] (MSE) which helps assessing the accuracy of the predictive models by measuring the average squared difference between the predicted values and the actual values in the dataset.  

Below is the the mathematical cost function 

![[Pasted image 20250409185250.png]]

![[Pasted image 20250409185320.png]]

Below is an easier way to understand

![[Pasted image 20250409191323.png]]

Where:

m = number of data points or training examples
y^ (y-hat) = predictions made by the model
y = actual data 

We are just taking the average (1/2m) over all the submission (m) of difference of the actual data (y) minus predictive data (y^) squared.

Minimize the the cost function towards zero to get the best and most accurate model