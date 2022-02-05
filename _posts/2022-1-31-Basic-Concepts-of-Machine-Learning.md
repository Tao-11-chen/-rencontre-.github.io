# Basic concepts of Machine Learning 

## 1.Componments of statistical learning
- supervised learning:learning a model and make the model outputs a good prediction for an given input.the dataset of the model should have a label
- unsupervised learning:make the computer to learn some internal rules itself.the dataset of unsupervised do not have any label
- semi-supervised learning:it's hard to tag large amount of data,SSL is a combination of supervised learing and unsupervised learning,
the dataset contains small amount of taged data(with label) and a large amount of data without label.
- reinforcement learning:supply an evalution of the action and the machine try itself to do a better action to make the evalution better

## 2.Basic concepts of supervised learning
- input space:Set of all possible values enters
- output space：Set of all possible values outputs
- feature space:Every input is called an instance,it can be represtended as feature vectors and the space where the feature vectors exists is the feature spcae.
**Noting that sometimes, in some model,feature space is the same as input space,we don't distinguish them.but in the other models,you should mapping or extract 
instances from input space to feature space cus the models are defined on the feature space actually.**
- hypothesis space:the purpose of the supervised learning is to learn a model to describe the input and output's relationship,it's actually a set of input-space's
mapping to output-space.

## 3.model,strategy and algorithm
### model:
the priority of Ml is find the suitable model,too complex model may lead to overfitting and too simple model may comes to under fitting problem
### strategy:
with model chosen,then we need to consider how to train the model,here we use loss function(cost function) to evaluate a prediction's quality,there's many different cost functions,List some below:
- MSE(L2 loss):Mean Squared Error

<img src="https://latex.codecogs.com/svg.image?J&space;=&space;\frac{1}{N}\sum_{i=1}^{N}\left&space;(&space;y_{i}&space;-&space;\hat{}y_{i}&space;\right&space;)^{2}" title="J = \frac{1}{N}\sum_{i=1}^{N}\left ( y_{i} - \hat{}y_{i} \right )^{2}" />

- MAE(L1 loss):Mean Absolute Error Loss

<img src="https://latex.codecogs.com/svg.image?J&space;=&space;\frac{1}{N}\sum_{i=0}^{N}\left|&space;y_{i}&space;-&space;y_{i}^{\hat{}}\right|" title="J = \frac{1}{N}\sum_{i=0}^{N}\left| y_{i} - y_{i}^{\hat{}}\right|" />

- Huber：a combination of L1 and L2 loss.when δ~0,Huber will be MAE;when δ ~ ∞,Huber will be MSE

![image1](https://s3.bmp.ovh/imgs/2022/02/301bf229574fcd14.png)

- Quantile: Pay more attention to interval prediction rather than point prediction

![image2](https://s3.bmp.ovh/imgs/2022/02/2e4607463f04943b.png)

- Cross Entropy: most common lossfunction in classfication tasks.

![image3](https://s3.bmp.ovh/imgs/2022/02/229925a3fb2f63af.jpg)

**The results derived by minimizing cross entropy are consistent with those obtained by maximizing likelihood** 

So，Cross Entropy is the same as maximum likelihood loss(log loss)

- 0/1: Not so common,used by perceptron.
<img src="https://latex.codecogs.com/svg.image?L\left&space;(&space;Y,&space;f\left&space;(&space;X&space;\right&space;)&space;\right&space;)&space;=\left\{\begin{aligned}1&space;&space;,&space;Y&space;\neq&space;&space;f\left&space;(&space;x&space;\right&space;)&space;\\0&space;&space;,&space;Y&space;=&space;f\left&space;(&space;x&space;\right&space;)&space;\\\end{aligned}\right.&space;" title="L\left ( Y, f\left ( X \right ) \right ) =\left\{\begin{aligned}1 , Y \neq f\left ( x \right ) \\0 , Y = f\left ( x \right ) \\\end{aligned}\right. " />

### algorithm:
Above two steps outputs a best model,then you need an algorithm to solve the model(optimization problem) 


## 3.Overfitting,generalization ability
Using complex model to describe simple problem will cause overfitting and lose generalization ability,
using simple model to solve complex problem will face underfitting. 

we use methods like regularization,cross validation to **choose a simple but adequate model**

Then we may face **lack of generalization ability**,do researches on generalization error bound to polish the model.

## 4.generative approach and discriminative approach

### generative approach
- typical generative models:Naive Bayes Model，Hidden Markov Model(HMM)，DBN，Markov Random Field
- If the model learns to recognize a sheep,it outputs the probability that cow == sheep is lower than 0.5

### discriminative approach
- typical discriminative models:SVM, logistic regression,Decision tree,k-nearest neighbor(KNN)
- If the model learns to recognize a sheep,it outputs false for cow == sheep 

![image](https://s3.bmp.ovh/imgs/2022/02/7d820adfdb22e775.jpg)

## 5. classfication,tagging,regression
### classfication
- outputs classes
- data are offen Discrete

### tagging
- outputs tagged sequence or state sequence

### regression
- outputs predicted data(real-valued output)
- data are offen successive
