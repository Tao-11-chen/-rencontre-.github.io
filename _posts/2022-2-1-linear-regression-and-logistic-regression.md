# This is a note on liner regression and logistic regression

## Liner regression
As we known before,the normal method of machine learning is to define a hypothesis space(model) and using a strategy and algorithm
to find the best parameter in the model.It's the same in Liner regression:

### 1.model:
We suppose that the data is approximately linear and define the model as:


<img src="https://latex.codecogs.com/svg.image?f\left&space;(&space;x&space;\right&space;)&space;=&space;W_{0}&space;&plus;&space;W_{1}X_{1}&space;&plus;&space;W_{2}X_{2}&space;&plus;&space;......&space;&plus;&space;W_{n}X_{n}" title="f\left ( x \right ) = W_{0} + W_{1}X_{1} + W_{2}X_{2} + ...... + W_{n}X_{n}" />

### 2.matrix form:

predict = f(x) = XW;

<img src="https://latex.codecogs.com/svg.image?W&space;=&space;\begin{bmatrix}W_{0}&space;\\W_{1}&space;\\W_{2}&space;\\.&space;\\.&space;\\W_{n}\end{bmatrix}" title="W = \begin{bmatrix}W_{0} \\W_{1} \\W_{2} \\. \\. \\W_{n}\end{bmatrix}" />

<img src="https://latex.codecogs.com/svg.image?X&space;=&space;\begin{bmatrix}1&space;&&space;&space;X_{1}^{1}&&space;&space;...&&space;X_{n}^{1}\\1&space;&&space;&space;X_{1}^{2}&&space;&space;...&&space;X_{n}^{2}\\...&space;&&space;&space;...&&space;&space;...&&space;...\\1&space;&&space;&space;X_{1}^{m}&&space;...&&space;X_{n}^{m}\\\end{bmatrix}" title="X = \begin{bmatrix}1 & X_{1}^{1}& ...& X_{n}^{1}\\1 & X_{1}^{2}& ...& X_{n}^{2}\\... & ...& ...& ...\\1 & X_{1}^{m}& ...& X_{n}^{m}\\\end{bmatrix}" />

**In data X:**

**"n" is the number of features,"m" is the number of datas, Insert "1" in the first line to represent W0**

### 3.strategy:

Then we should to find a strategy to find a series of **W** to make **f(x) = XW** similar to the label **y**.

Using Mean Squared Error here:

<img src="https://latex.codecogs.com/svg.image?J&space;=&space;\frac{1}{N}\sum_{i=1}^{N}\left&space;(&space;y_{i}&space;-&space;\hat{}y_{i}&space;\right&space;)^{2}" title="J = \frac{1}{N}\sum_{i=1}^{N}\left ( y_{i} - \hat{}y_{i} \right )^{2}" />

### 4.algoritm
Then we need to use an algorithm to minimize MAE loss.In Liner regression,we got two methods here:**Normal equation and 
gradient descent**

#### gradient descent
This is a general method to minimize loss function,using Andrew Ng's explain here:

Imagine that we graph our hypothesis function based on its fields theta0 and theta1
(actually we are graphing the cost function as a function of the parameter estimates). 
We are not graphing x and y itself, but the parameter range of our hypothesis function and the cost resulting from selecting a particular set of parameters.
  
We put theta0 on the x axis and theta1 on the y axis, with the cost function on the vertical z axis. The points on our graph will be the result of the cost function using our hypothesis with those specific theta parameters. The graph below depicts such a setup.

![image1](https://s3.bmp.ovh/imgs/2022/02/7d9be7d6fa964c39.png)

We will know that we have succeeded when our cost function is at the very bottom of the pits in our graph, i.e. when its value is the minimum.  The red arrows show the minimum points in the graph.

The way we do this is by taking the derivative (the tangential line to a function) of our cost function. The slope of the tangent is the derivative at that point and it will give us a direction to move towards. We make steps down the cost function in the direction with the steepest descent. The size of each step is determined by the parameter α, which is called the learning rate. 

For example, the distance between each 'star' in the graph above represents a step determined by our parameter α. A smaller α would result in a smaller step and a larger α results in a larger step. The direction in which the step is taken is determined by the partial derivative of J(θ0,θ1).
Depending on where one starts on the graph, one could end up at different points. The image above shows us two different starting points that end up in two different places.

The gradient descent algorithm is:

repeat until convergence:

<img src="https://latex.codecogs.com/svg.image?\theta_{j}&space;=&space;\theta_{j}&space;-&space;\alpha&space;\frac{\vartheta&space;}{\vartheta&space;\theta_{j}}&space;J\left&space;(&space;\theta&space;_{0},\theta_{1}&space;\right&space;)" title="\theta_{j} = \theta_{j} - \alpha \frac{\vartheta }{\vartheta \theta_{j}} J\left ( \theta _{0},\theta_{1} \right )" />

j=0,1 represents the feature index number.

**However,this is batch gradient descent(BGD),it computes all the grades and is slow,so we have Stochastic Gradient Descent(SGD) and Mini-batch Gradient Descent(MGD)
,they are faster in calculation and is well performed too.**

#### Normal equation
Gradient descent gives one way of minimizing J. Let’s discuss a second way of doing so, this time performing the minimization explicitly and without resorting to an iterative algorithm. In the "Normal Equation" method, we will minimize J by explicitly taking its derivatives with respect to the θj ’s, and setting them to zero. This allows us to find the optimum theta without iteration. The normal equation formula is given below: 

<img src="https://latex.codecogs.com/svg.image?\theta&space;=&space;\left&space;(X^{T}X&space;\right&space;)^{-1}X^{T}y" title="\theta = \left (X^{T}X \right )^{-1}X^{T}y" />

With the normal equation, computing the inversion has complexity <img src="https://latex.codecogs.com/svg.image?O\left&space;(&space;&space;n^{3}\right&space;)" title="O\left ( n^{3}\right )" />. So if we have a very large number of features, the normal equation will be slow. In practice, when n exceeds 10,000 it might be a good time to go from a normal solution to an iterative process.

**But**,the X*TX maybe **noninvertible**,you should deleting a feature 
that is linearly dependent with another or deleting one or more features when there are too many features.

## Logistic regression




