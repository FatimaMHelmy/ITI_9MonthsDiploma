## Q1:Explain briefly batch gradient descent, stochastic gradient descent, and mini-batch gradient descent? and what are the pros and cons for each of them?

### **Gradient descent**
Gradient descent is a generic optimization algorithm cable for finding optimal solutions to a wide range of problems. The general idea of gradient descent is to tweak parameters iteratively in order to minimize a cost function.

Batch Gradient Descent: In Batch Gradient descent the whole training data is used to minimize the loss function by taking a step towards the nearest minimum by calculating the gradient (the direction of descent)
**** PATCH == NUM OF OBSERVATIONS

![image](https://user-images.githubusercontent.com/84232181/211675112-e991c8ee-4241-4137-97f6-be00b033ad36.png)


Pros: Since the whole data set is used to calculate the gradient it will be stable and reach the minimum of the cost function without bouncing (if the learning rate is chosen cooreclty)

Cons:

Since batch gradient descent uses all the training set to compute the gradient at every step, it will be very slow especially if the size of the training data is large.

### Stochastic Gradient Descent:

Stochastic Gradient Descent picks up a random instance in the training data set at every step and computes the gradient-based only on that single instance.

![image](https://user-images.githubusercontent.com/84232181/211434083-53fdcc31-683a-4405-87b3-d5fa4e4d0e3b.png)

**** PATCH == 1
Pros:

    It makes the training much faster as it only works on one instance at a time.
    It become easier to train large datasets

Cons:

Due to the stochastic (random) nature of this algorithm, this algorithm is much less regular than the batch gradient descent. Instead of gently decreasing until it reaches the minimum, the cost function will bounce up and down, decreasing only on average. Over time it will end up very close to the minimum, but once it gets there it will continue to bounce around, not settling down there. So once the algorithm stops the final parameter are good but not optimal. For this reason, it is important to use a training schedule to overcome this randomness.

**Mini-batch Gradient**:

At each step instead of computing the gradients on the whole data set as in the Batch Gradient Descent or using one random instance as in the Stochastic Gradient Descent, this algorithm computes the gradients on small random sets of instances called mini-batches.

**** PATCH == NUM OF OBSERVATIONS / EPOCKS
Pros:

    The algorithm's progress space is less erratic than with Stochastic Gradient Descent, especially with large mini-batches.
    You can get a performance boost from hardware optimization of matrix operations, especially when using GPUs.

Cons:

    It might be difficult to escape from local minima.

![image](https://user-images.githubusercontent.com/84232181/211414414-b2949135-580b-40ea-8e55-f041371e15fb.png)

## Q2: WHY WE USE Momentum Based Gradient Descent?
Suppose during optimizing our model, we reach a point where the slope or gradient at that point is flat or Δw → 0, in this case, our update to the parameter will be very small or there will be no update. Since w = w- ηΔw.

In this case, our optimization algorithm may get stuck in the plateau region and it will slow our learning process. Vice versa on steep regions the gradient descent works very fast since the gradient is high.

So, because of this uneven optimization speed at different points on the graph, weights initialization or starting point for gradient descent algorithm can be a deciding point for how our model will perform.

** THE EQUATION OF WEIGHTS UPDATE CHANGED FRON 1 TO 2 **:

1:

 ![image](https://user-images.githubusercontent.com/84232181/211419314-43412fc7-0bb7-4d96-93ae-29b123f0f209.png)

2:

![image](https://user-images.githubusercontent.com/84232181/211418589-6b729037-6da6-46dd-a878-21743f21bc6f.png)

**!HINT**

![image](https://user-images.githubusercontent.com/84232181/211423267-a5c46aef-1b2e-450c-8fa8-6750869d6bb4.png)


**Advantage** of Momentum Based Gradient Descent

    It will update quickly even on plateau regions of gradient descent graph, unlike gradient descent algorithm.

**The disadvantage** of Momentum Based Gradient Descent

    Due to high momentum gained, it may overshoot and take time to converge
    It oscillates in and out of the minima valley

Despite these disadvantages, it still converges faster than gradient descent.

