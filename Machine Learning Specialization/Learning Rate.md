The learning rate is known as the symbol alpha or $\alpha$. It is a positive value and we want to choose a rate which is not too big or small as it can lead to convergence on gradient descent to overshoot or even fail. We will know when gradient descent is working correctly when the learning curve which measures the cost function vs the number of iterations is going down and we will know when we have likely reached convergence, when the learning curve starts to plateau. As shown below:

![[Pasted image 20250420162409.png]]

Note that how many iterations we need for the model to converge depends of each model and can vary. We can also do an automatic test to know when we are close to convergence by setting the value of epsilon or shown as $\epsilon$ and if the cost function decreases by less than the value of $\epsilon$ in on iteration we can declare convergence.

Again to clarify, if the cost function if increasing at any point during gradient descent there is a problem with either the code or the learning rate it too large and is overshooting. We can identifying the bug in the code. If the learning rate is too large we simply and use a smaller learning rate so the cost function decreases after every iteration.![[Pasted image 20250420163533.png]]

Once we have fixed the problem we should try to correct the learning rate so our model is efficient as learning rate which is too small will lead to more compute and an less efficient model. This can be done by experimenting and trying different values of learning rate ($\alpha$) so we get the model whose cost function decreases most gradually over the number of iterations.
![[Pasted image 20250420163838.png]]