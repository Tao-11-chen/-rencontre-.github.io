---
layout: post
title: SVM together with HOG feature extraction algorithm
date: 2021-11-29 23:18 +0800
last_modified_at: 2022-1-2 01:08:25 +0800
tags: [AI]
toc:  true
---
Welcome to my first blog!This is an introduction to support vector machines.
{: .message }

it's my first time learning about machine learning or AI,SVM is simple in theory compared with modern AI methods like CNN,i do think it's a great method

## Disadvantages and advantages of SVM
1.advantages:
  - The theory of this method is very clear and can be clearly proved by mathematics,can be transformed into typical Lagrange multiplier method(well,maybe just a advantage for me:I've just learned Advanced mathematics and knows how to solve it.)
  - Support vector is the training result of SVM, and it plays a core role in SVM classification decision-making; A few support vectors determine the model's results, which makes the algorithm more robust.
  - It belongs to convex optimization problem, so the local optimal solution must be the global optimal solution.
2.disadvantages:
  - SVM is difficult to implement for large data training. Because SVM solves the support vector with the help of quadratic programming, it involves the calculation of m-order matrix, which consumes a lot of space and time. The improved method to solve the above problems is SMO algorithm.
  - Classical SVM only gives two classification algorithms, but in practice, there is more multi classification problem, so we usually solve it by constructing a combination of multiple two classification support vector machines. The first mock exam is one to many patterns, one to one mode and SVM decision tree.
  - The choose of the Kernel(methods to project to high dimensional space) is more depended on experiences,lack of objective law(maybe not found yet)
  
## Processes of SVM
first,we got a problem now,how to classify the two vector:The column y indicates if the email qualifies as spam or no spam.
![image](https://github.com/Tao-11-chen/Tao-11-chen.github.io/blob/master/_posts/1png.png)
Hence, we have a binary classification challenge. We will use a linear model to build the classifier.
![image](https://github.com/Tao-11-chen/Tao-11-chen.github.io/blob/master/_posts/2.png)
