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


- Huber
- Quantile
- Cross Entropy
- Hinge
- 0/1
### algorithm:
