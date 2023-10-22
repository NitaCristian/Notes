
# Applications

Rank web pages in a web search
Recognize people in pictures
Recommendations
Speech recognition 
Filter spam emails


It is a sub field of AI.
Don't know how to write an explicit program to do perform web search, recognize speech, diagnose diseases or build a self-driving card.


# Definition

"Field of study that gives computers the ability to learn without being explicitly programmed."" - Arthur Samuel

# Algorithms

Supervised learning - used most in real-world application

Unsupervised learning
Recommender systems
Reinforcement learning

# Supervised learning

Algorithms that learn x to y, or input to output mappings.

A key characteristic is that you give your algorithm examples to learn from that includes the right answers.
The correct answers means the correct label y for a given input x.

Seeing correct pairs of input x and desired output y that the learning algorithms learns to take the input alone and give an accurate prediction of the output.


| Input (x) | Output (y) | Application|
|-----------|------------|------------|
|email | spam (0/1)| spam filter|
|audio | text transcript | speech recognition|
|English | Spanish | machine translation|
|ad, user info| click (0/1) | online advertising|
|image, radar info| positions of other cars| self-driving car|
|image of phone| defect (0/1)| visual inspection|


Regression: Predict housing prices based on house size.
The correct price y given for every house size x.

Regression - predict a number from an infinitely many possible numbers

second major type - classification

Breast cancer detection

using a patient's medical records, ml tries to figure out if a tumor (lump of cells) is malignant (cancerous) or benign (just a lump) 

output is only two values, 0 or 1, meaning benign or malignant
predict only a small number of categories, two in this case
in regression you try to predict a number from an infinitely number of possible outputs.

classification
output class = output categories
classification algorithms predict categories, can be non-numeric
whether a picture is a cat or dog.

plot a graph for tumor size and age
the algorithms might find a boundary line to separate the two categories

# Unsupervised learning


Supervised - learn from labeled with the right answers

Unsupervised - no labels,
find a pattern, a structure, something interesting
we are not supervising the algorithm, we are not giving it the right answers.

it can decided to separate the data into clusters
Clustering algorithm

google news - look at articles and group them together
group similar articles about something from different news outlets.


clustering genetic dna
dna microarray
genes for each row, person for each column
how much certain genes are expressed for each person


grouping customers

# Linear regression model

Dataset: house sizes and prices from Portland

![[Pasted image 20231022122257.png]]

Problem: You are a real estate agent in Portland and you're helping a client to sell her house. She is asking you, how much do you think I can get for this house?

You start by measuring the size of the house, and it turns out that the house is 1250 square feet.
How much do you think this house could sell for?

You can build a linear regression model from this dataset. Your model will fit a straight line to the data, which might look like this.

This is an example of what's called a supervised learning model. We call this supervised learning because you are first training a model by giving a data that has right answers because you get the model examples of houses with both the size of the house, as well as the price that the model should predict for each house.

It's called regression model because it predicts numbers as the output like prices in dollars. Any supervised learning model that predicts a number such as 220,000 or 1.5 or negative 33.2 is addressing what's called a regression problem.

As a reminder about the difference between classification and regression, in classification, there are only a small number of possible outputs.

![[Pasted image 20231022122611.png]]

## Terminology

The dataset that is used to train the model is called a training set.
The input variable is noted as x. Also called a feature or input feature.
The output variable is also called the target variable is called y.
Each row is a different training example.
The total number of training examples is called m.
A single training example uses the notation (x, y).
To refer to a specific training example we use $(x^{(i)}, y^{(i)})$. 
The superscript tells use this is the $i^{th}$ training example.

![[Pasted image 20231022123424.png]]


A training set includes the input features and the output targets.
To train the model, you feed the training set to the learning algorithm. 
The supervised learning algorithm will produce a function f, also called a hypothesis.
The job of the function is to take a new input x and output an estimate or prediction called $\hat{y}$.
The function is called the model, and the output is the prediction (estimate y).

The function f is going to be represented as $f_{w,b}(x) = wx + b$. W and B are number and their values will determine the prediction based on the input feature x.

![[Pasted image 20231022124224.png]]

# Cost function

It tells us how well the model is doing.

w and b are called the parameters of the function $f_{w,b}(x) = wx + b$.
You can adjust them during training. Another name for them is coefficients or weights.

$\hat{y}^{(i)} = f_{w,b}(x) = wx + b$.
How to find values for w and b so that the prediction $\hat{y}$ is close to $y^{(i)}$ for all $(x^{(i)}, y^{(i)})$?

The cost function takes the prediction and compares it to the target y.
It takes $(\hat{y} - y)$. This difference is called the error.
The we compute the square of this error.
And also compute this for every training example, $(\hat{y}^{(i)} - y^{(i)})^2$.
We want to measure the error across the entire dataset, particularly the sum of the squared errors.
To build a cost function that doesn't get bigger as the size of the training set gets larger, we are going to compute the average squared error.
By convention, the cost function divides by 2m. It is used to make later calculations easier.
$$
J(w,b) = \frac{1}{2m} \sum^m_{i=1}(\hat{y}^{(i)} - y^{(i)})^2
$$
The squared error cost function.

![[Pasted image 20231022125731.png]]

# Gradient descent