Cost Function
Goals :-
implement and explore the cost function for linear regression with one variable.
Tools :-
NumPy, a popular library for scientific computing
Matplotlib, a popular library for plotting data
local plotting routines in the lab_utils_uni.py file in the local directory
Problem Statement
You would like a model which can predict housing prices given the size of the house.
Let's use the same two data points as before the previous lab- a house with 1000 square feet sold for $300,000 and a house with 2000 square feet sold for $500,000.
Computing Cost
The term 'cost' in this assignment might be a little confusing since the data is housing cost. Here, cost is a measure how well our model is predicting the target price of the house. The term 'price' is used for housing data.

The equation for cost with one variable is:
𝐽(𝑤,𝑏)=12𝑚∑𝑖=0𝑚−1(𝑓𝑤,𝑏(𝑥(𝑖))−𝑦(𝑖))2(1)
where
𝑓𝑤,𝑏(𝑥(𝑖))=𝑤𝑥(𝑖)+𝑏(2)
𝑓𝑤,𝑏(𝑥(𝑖))
  is our prediction for example  𝑖
  using parameters  𝑤,𝑏
 .
(𝑓𝑤,𝑏(𝑥(𝑖))−𝑦(𝑖))2
  is the squared difference between the target value and the prediction.
These differences are summed over all the  𝑚
  examples and divided by 2m to produce the cost,  𝐽(𝑤,𝑏)
  Cost Function Intuition
  Our goal is to find a model  𝑓𝑤,𝑏(𝑥)=𝑤𝑥+𝑏
 , with parameters  𝑤,𝑏
 , which will accurately predict house values given an input  𝑥
 . The cost is a measure of how accurate the model is on the training data.

The cost equation (1) above shows that if  𝑤
  and  𝑏
  can be selected such that the predictions  𝑓𝑤,𝑏(𝑥)
  match the target data  𝑦
 , the  (𝑓𝑤,𝑏(𝑥(𝑖))−𝑦(𝑖))2
  term will be zero and the cost minimized. In this simple two point example
  The plot contains a few points that are worth mentioning.

cost is minimized when  𝑤=200
 , which matches results from the previous lab
Because the difference between the target and pediction is squared in the cost equation, the cost increases rapidly when  𝑤
  is either too large or too small.
Using the w and b selected by minimizing cost results in a line which is a perfect fit to the data.
Cost Function Visualization- 3D:-
You can see how cost varies with respect to both w and b by plotting in 3D or using a contour plot.
The routines are in lab_utils_uni.py in the local directory.
 
