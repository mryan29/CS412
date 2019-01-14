# Day one - Machine Learning

What is machine learning? An algorithm which improves itself with exposure to data.

ML algorithms build model of data and then make predictions based on that model. As much about the process as it is the resulting model.

# Types of problems

**supervised**: 
- algorithm builds model based on given training data
- easier to get an understanding of how *good* a model is
- give it data where we already know the answer, the bulk of our class

**unsupervised**:
- some stream of data, relying on computer to build model of patterns
- no *known* value for data points, model just tries to build trends and see patterns

What does good machine learning look like?
- data driven (not by personal bias, ideas)
- statistically validated 
- understanding of the problem space

# about the course
USPS Mail Data
- "1"s and "5"s

5 assignments
- LaTex/RMD
- will contain both written and code portions
- due wednesdays

Final project
- individual, data of your choice
- suggest UCI data, etc.

Languages "officically" supported: R and Python
- common/easy to use for data science/machine learning

One midterm
- march 15th, in class, end of week 9

No final exam, final projects will be due wednesday of finals week

Textbook: The Elements of Statistical Learning, Hastie Tibshirani Friedman
- not required, just picked because among the cheaper versions

Topics List:
- supervised learning
  - regression, nearest-neighbors, support vector machines, neural networks, ensemble methods
- data handling
  - pre-processing, feature selection, concentration bounds, biased data, noise/outlier detection
- graphical models
  - markov graphs, decision trees, bayes networks
- unsupervised learning
  - clustering, k-Cover
- if we have time topics

# Start of Material
Rock, paper, scissors - design an algo that plays

Note: we are not trying to model the actual game, but instead model the opponents strategy (I think)

Algo 1: choose rock
- what's wrong with it? we win 1/3 of the time if opposition is totally unpredictable aka this is **predictable**
- normally, predictability is a good thing, but here if the opponent has info about how you'll perform, then they have an advantage

Algo 2: choose at random
- if playing against someone who is random, then its still winning 1/3 of time
- if playing against someone who always picks rock, still winning 1/3 of time
- hard to predict
- should win about 1/3 of time and draw 1/3 of time
- possible improvements: 

Algo 3: keep table of all moves opponent makes and choose on that beats its most common choice and random if tie
- what does this algo try to exploit:
  - we're allowing ourselves to take advantage of a data bias if it exists (beats the "all-rock" opponent)
  - however, this is roughly the same as the random opponent
  - what if the opposing player finds out that this is my strategy? (always an advantage)
    - will want to force things to be equally distributed if this is the case to make it harder

What does this problem suppose?
- the opposing player ust have some level of predictability

*human beings are exploitable in very predictable ways*

Algo 4: record all previous chocices of opponent, shove it into a ml algorithm and then let the prediction variable be the next throw
- what's wrong with this approach? from CS perspective, each piece of data has differing width

suppose we adjust this by doing: algo 4: keep record of last 3 throws and see what opposing player usually throws next (can make a state machine)

This is called a markov-model
- porbability based graph, good at solving turn-based sort of prediction problems w discrete states
- update probs for each val as we plpay (reinforcement + machine learning)
- how accurate? cant quantify yet --> see rps context to try
- what else could be solved w this approach: 


Self note: this is very similar to my lectures in game theory, maybe go back and review some of those lectures
