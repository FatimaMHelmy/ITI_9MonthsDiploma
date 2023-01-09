## Q1:Explain briefly batch gradient descent, stochastic gradient descent, and mini-batch gradient descent? and what are the pros and cons for each of them?

Gradient descent is a generic optimization algorithm cable for finding optimal solutions to a wide range of problems. The general idea of gradient descent is to tweak parameters iteratively in order to minimize a cost function.

Batch Gradient Descent: In Batch Gradient descent the whole training data is used to minimize the loss function by taking a step towards the nearest minimum by calculating the gradient (the direction of descent)

Pros: Since the whole data set is used to calculate the gradient it will be stable and reach the minimum of the cost function without bouncing (if the learning rate is chosen cooreclty)

Cons:

Since batch gradient descent uses all the training set to compute the gradient at every step, it will be very slow especially if the size of the training data is large.

Stochastic Gradient Descent:

Stochastic Gradient Descent picks up a random instance in the training data set at every step and computes the gradient-based only on that single instance.

Pros:

    It makes the training much faster as it only works on one instance at a time.
    It become easier to train large datasets

Cons:

Due to the stochastic (random) nature of this algorithm, this algorithm is much less regular than the batch gradient descent. Instead of gently decreasing until it reaches the minimum, the cost function will bounce up and down, decreasing only on average. Over time it will end up very close to the minimum, but once it gets there it will continue to bounce around, not settling down there. So once the algorithm stops the final parameter are good but not optimal. For this reason, it is important to use a training schedule to overcome this randomness.

Mini-batch Gradient:

At each step instead of computing the gradients on the whole data set as in the Batch Gradient Descent or using one random instance as in the Stochastic Gradient Descent, this algorithm computes the gradients on small random sets of instances called mini-batches.

Pros:

    The algorithm's progress space is less erratic than with Stochastic Gradient Descent, especially with large mini-batches.
    You can get a performance boost from hardware optimization of matrix operations, especially when using GPUs.

Cons:

    It might be difficult to escape from local minima.

![image](https://user-images.githubusercontent.com/84232181/211414414-b2949135-580b-40ea-8e55-f041371e15fb.png)
