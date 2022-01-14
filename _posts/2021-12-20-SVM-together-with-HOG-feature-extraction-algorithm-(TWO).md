  
## Processes of Soft Margin Classifier

So far we have assumed that it is always possible to find a line that will separate positive and negative cases. However, most of the real data set have no such hyper planes. See the data set below:
![image17]()

In such cases, we need to introduce a penalty C associated to the number of mistakes, while maintaining high margins at the same time.
![image]

So now the goal is to define a hyperplane that gives good margins, yet is allowed to make a few mistakes.
![image]

But not all mistakes are equal. We will use slack variables ε, or penalties for wrongly classifying data.
ε is the distance from other side of the margin to the data point itself.
![image]

Now our goal is to find w ,b, ε in such a way that the optimization is achieved. If x is on the wrong side of the margin, we incur loss of ε.
**C is called slack penalty, as it acts as a tuning parameter of how much we wish to maximize the margin versus penalizing our classification mistakes.**
![image]
![image]

The loss function for SVM is called hinged loss, and it looks like the red line below. The loss function is hinged on the point marked K:
![image]

