Gradient Descent for Linear Regression
Goals
automate the process of optimizing  𝑤 and  𝑏using gradient descent.
Tools
NumPy, a popular library for scientific computing
Matplotlib, a popular library for plotting data
plotting routines in the lab_utils.py file in the local directory
# Problem Statement

Let's use the same two data points as before - a house with 1000 square feet sold for \\$300,000 and a house with 2000 square feet sold for \\$500,000.

| Size (1000 sqft)     | Price (1000s of dollars) |
| ----------------| ------------------------ |
| 1               | 300                      |
| 2               | 500                      |
Gradient descent summary
So far in this course, you have developed a linear model that predicts  𝑓𝑤,𝑏(𝑥(𝑖))
 :
𝑓𝑤,𝑏(𝑥(𝑖))=𝑤𝑥(𝑖)+𝑏(1)
In linear regression, you utilize input training data to fit the parameters  𝑤
 , 𝑏
  by minimizing a measure of the error between our predictions  𝑓𝑤,𝑏(𝑥(𝑖))
  and the actual data  𝑦(𝑖)
 . The measure is called the  𝑐𝑜𝑠𝑡
 ,  𝐽(𝑤,𝑏)
 . In training you measure the cost over all of our training samples  𝑥(𝑖),𝑦(𝑖)
 
𝐽(𝑤,𝑏)=12𝑚∑𝑖=0𝑚−1(𝑓𝑤,𝑏(𝑥(𝑖))−𝑦(𝑖))2(2)
gradient descent was described as:

repeat𝑤𝑏} until convergence:{=𝑤−𝛼∂𝐽(𝑤,𝑏)∂𝑤=𝑏−𝛼∂𝐽(𝑤,𝑏)∂𝑏(3)
where, parameters 𝑤
, 𝑏
 are updated simultaneously.
The gradient is defined as:
∂𝐽(𝑤,𝑏)∂𝑤∂𝐽(𝑤,𝑏)∂𝑏=1𝑚∑𝑖=0𝑚−1(𝑓𝑤,𝑏(𝑥(𝑖))−𝑦(𝑖))𝑥(𝑖)=1𝑚∑𝑖=0𝑚−1(𝑓𝑤,𝑏(𝑥(𝑖))−𝑦(𝑖))(4)(5)
Here simultaniously means that you calculate the partial derivatives for all the parameters before updating any of the parameters
Implement Gradient Descent
You will implement gradient descent algorithm for one feature. You will need three functions.

compute_gradient implementing equation (4) and (5) above
compute_cost implementing equation (2) above (code from previous lab)
gradient_descent, utilizing compute_gradient and compute_cost
Conventions:

The naming of python variables containing partial derivatives follows this pattern, ∂𝐽(𝑤,𝑏)∂𝑏
  will be dj_db.
w.r.t is With Respect To, as in partial derivative of  𝐽(𝑤𝑏)
  With Respect To  𝑏
Gradient Descent
Now that gradients can be computed, gradient descent, described in equation (3) above can be implemented below in gradient_descent. The details of the implementation are described in the comments. Below, you will utilize this function to find optimal values of  𝑤
  and  𝑏
  on the training data.
