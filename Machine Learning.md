
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