---
layout: post
title: SVM Together With HOG Feature Extraction Algorithm(ONE)
date: 2021-11-8 23:18 +0800
last_modified_at: 2021-11-8 01:08:25 +0800
tags: [AI]
toc:  true
---

# This is an introduction to support vector machines and HOG.

it's my first time learning about machine learning,SVM is simple in theory compared with modern AI methods like CNN but is well performanced.

## Disadvantages and advantages of SVM

### 1.advantages:
  - The theory of this method is very clear and can be clearly proved by mathematics,can be transformed into typical Lagrange multiplier method(well,maybe just a advantage for me:I've just learned Advanced mathematics and knows how to solve it.)
  - Support vector is the training result of SVM, and it plays a core role in SVM classification decision-making; A few support vectors determine the model's results, which makes the algorithm more robust.
  - It belongs to convex optimization problem, so the local optimal solution must be the global optimal solution.
### 2.disadvantages:
  - SVM is difficult to implement for large data training. Because SVM solves the support vector with the help of quadratic programming, it involves the calculation of m-order matrix, which consumes a lot of space and time. The improved method to solve the above problems is SMO algorithm.
  - Classical SVM only gives two classification algorithms, but in practice, there is more multi classification problem, so we usually solve it by constructing a combination of multiple two classification support vector machines. The first mock exam is one to many patterns, one to one mode and SVM decision tree.
  - The choose of the Kernel(methods to project to high dimensional space) is more depended on experiences,lack of objective law(maybe not found yet)
 
## Classification of SVM methods:
  - linear support vector machine in linearly separable case  
  
      used when the data is completely linearly separable,also called **hard margin maximization**.
  - linear support vector machine  
  
      used when the data is approximately linearly separable,also called **soft margin maximization**.
  - non-linear support vector machine  
  
      used when the data is completely not linearly separable,using **soft margin maximization together with kernal trick**.
  
## Processes of SVM (hard constraints)

first,we got a problem now,how to classify the two vector:The column y indicates if the email qualifies as spam or no spam.

![image1](https://s3.bmp.ovh/imgs/2022/01/263690e569eb59bc.png)

Hence, we have a binary classification challenge. We will use a linear model to build the classifier.

![image2](https://s3.bmp.ovh/imgs/2022/01/04eb5d3d298e796a.png)

Hence our objective is to find values of W to define the function f(x)
Our goal now is to define a hyper plane — f(x) to classify spam from not spam emails by finding the values of W.
Shown in a XYZ system,is to draw a line to classify the data

![image3](https://s3.bmp.ovh/imgs/2022/01/57c280e847b34e57.png)

Then our aim is to define a line that best classifies our data as spam/not spam.
But how do we find the best line ?

![image4](https://s3.bmp.ovh/imgs/2022/01/28bf0bd7f028eb83.png)

The rationale behind choosing the line is that more the distance from the separating line, more the confidence in our classification and vice versa.

![image5](https://s3.bmp.ovh/imgs/2022/01/30147438341d0b50.png)

So now we want to find the line with the largest margin, or a line which maximizes the distance of the closest points across the line.
We will define margin as the distance of the closest example from the decision boundary. We will refer to the value of the decision boundary as γ.
γ in the left figure below is much lesser than γ in the right figure below

![image6](https://s3.bmp.ovh/imgs/2022/01/096c9f9b0126be10.png)

But how do we compute γ?

![image7](https://s3.bmp.ovh/imgs/2022/01/1f1536dcc2f2a1b1.png)

It can be shown mathematically that the distance of point A from L is wA+b.

![image8](https://s3.bmp.ovh/imgs/2022/01/fb08391f61f5c88d.png)

So now that we are able to find γ, we can work on finding w, and define the separating plane which has the largest margin.
The condition for finding W is:
For all our data points , if data point i has the smallest γ, we would want to maximize γ for the point i.

![image9](https://s3.bmp.ovh/imgs/2022/01/bcd080103d13a68f.png)

We can write this down as an optimization problem with a goal to find γ, so that for each training example the value of the largest training example is at least γ. And by finding γ, we will consequently find w.

![image10](https://s3.bmp.ovh/imgs/2022/01/70f86a4b8c3fe5b7.png)

Where does the term support vector come from ?
The name support vector comes from the fact that our large margin classifier is defined by only a very few points (or vectors).
In the example below, the classifier can be defined by only the three points, and we can safely ignore all the other points. Or we may say that the vector is supported by 3 points.

![image11](https://s3.bmp.ovh/imgs/2022/01/7ae66406a034f6a3.png)

Usually if we have d dimensional data, we require d+1 support vectors to define our line.

Let us assume we have a data point X, and we have calculated γ for point X.
From the equation below it can be seen that γ also scales, if we scale W. This will give a false estimate for γ, and impact our cost function.

![image12](https://s3.bmp.ovh/imgs/2022/01/1ba1332428ddb7c9.png)

There are 2 steps for solving this problem
1. We work with a normalized W;
![image13](https://s3.bmp.ovh/imgs/2022/01/b612df693ba73119.png)

2. We define our support vectors as **w×x + b = +-1**.
![image14](https://s3.bmp.ovh/imgs/2022/01/b5e8a99e7ae32c19.png)

How do we calculate γ?
![image15](https://s3.bmp.ovh/imgs/2022/01/c457c1a99505407b.png)

Hence, our constraints change to:
![image16](https://s3.bmp.ovh/imgs/2022/01/0557a8f62b30ba5b.png)

Now the problem of maximizing γ has changed to:
  **maintaining the constraint that our confidence in classification all data points is greater than 1 and minimizing the length of vector w.**

That is so called hard constraints.
