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
This is a general method to minimize loss function,

## Logistic regression




