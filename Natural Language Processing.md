
## Aims

- Introduce theoretical background and practical applications of NLP
- Connections with other fields 
- Analyze and discuss real-world problems

## Objectives

- Explain differences between rule-based and statistical approaches
- Select appropriate statistical language analysis techniques
- Use software tools such as corpus readers, stemmers, taggers and parsers
- Define formal grammars for fragments of a natural language
- Evaluate applications of statistical techniques

## NLP Perspectives

Computer/Data science
- Theoretical foundations of computation and practical techniques for implementation

Information science
- Analysis, classification, manipulation, retrieval and dissemination of information

Computational linguistics
- Use of computational techniques to study linguistic phenomena

Cognitive science 
- Study of human information processing (perception language, reasoning)

## NLP paradigms

Symbolic approaches:
- Rule-based, hand coded (by linguists, subject matter experts)
- Knowledge-intensive

Statistical approaches:
- Distributional & neural approaches, supervised or unsupervised
- Data-intensive

## NLP applications

- Text categorization

Media monitoring: classify incoming news stories and publish them to the right people

Search engines: classify query intent 

Spam detection

- Machine translation

Fully automatic: Google translate

Semi-automated: Helping human translators

- Text summarisation

Single-document / Multi-document
Search results
Word processing


- Dialog systems

Chat bots
Smart speakers
Smartphone assistants
Call handling systems

- Sentiment analysis

Identify and extract subjective information (opinions)

Sub-tasks:
- Identify polarity: positive, negative, neutral
- Identify emotional states: angry, sad, happy
- Subjectivity/objectivity identification
- Feature/aspect-based
	- Differentiate between specific features or aspects

- Text mining

Discover new knowledge from unstructured text resources

A<->B, B<->C
Infer A<->C
- link between migraine headaches and magnesium deficiency

- Question answering

Going beyond the document retrieval paradigm:
- provide specific answers to specific questions

- Natural language generation
- Speech recognition and synthesis

## History of NLP

Two foundational paradigms:
- the automaton
- information-theoretic models

The automaton arose out of Turing's model of algorithmic computation.

Chomsky considered finite state machines as a way to characterize a grammar.

Shannon borrowed the concept of entropy from thermodynamics:
- as a way of measuring information content of a language
- measured of the entropy of English by using probabilistic techniques
- measure of randomness

### Early NLP systems

ELIZA
- first chat bot
- uses pattern matching

SHDRLU
- natural language understanding
- comprehensive grammar of English

Examples of supervised machine learning tasks are:
- Semantic analysis 
- Topic classification
- Parsing

The driving forces behind the empiricist approaches of the 1990s were:
- The rise of the WWW
- Regular competitive evaluation exercises: events such as the Message Understanding Conference facilitated this approach

Entropy a measure of:
- Uncertainty, measure of randomness or disorder
## Evaluation

NLP tasks can be categorized by problem type:
- Classification: sentiment classification, news categorization
- Regression: essay sorting
- Sequence labelling: part of speech tagging, named entity recognition

### Example of classification

Spam classifier: Predict whether email messages should be filtered or not
Input: feature matrix (email message)
Output: target vector (yes, no)
Algorithm: Model could be Native Bayes, KNN, etc...
This is binary classification

### How it is done

Choose a model type (class of model)
Set model hyperparameters
Configure your data (x and y)
Fit the model to your data
Apply the model to new data

![[Pasted image 20231021145359.png]]

### Evaluating classifiers

What metric to use? Accuracy
1000 predictions -> 831 good

However, the dataset was unbalanced
If we pick the majority class, we will achieve 81.2% accuracy.
![[Pasted image 20231021145647.png]]

### Evaluation metrics

Accuracy is defined as the proportion of correct predictions over all predictions.
For an unbalanced data set we can achieve high accuracy simply by selecting the majority class.

Example: Predict whether a CT scan shows a tumor or not?

Tumors are rate events -> classes are unbalanced
The cost of missing a tumor is much higher than a false alarm.
Accuracy is not a good metric.

### Confusion matrix

Compare predicted with actual values:
- True positives -> predicted = positive, actual = positive
- False positives -> predicted = positive, actual = negative
- False negatives -> predicted = negative, actual = positive
- True negatives -> predicted = negative, actual, negative

![[Pasted image 20231021150331.png]]

![[Pasted image 20231021150345.png]]

Accuracy: Is the proportion of correct predictions over incorrect ones
Recall: The proportion of true positives over all the actual positives
Precision: The proportion of true positives over all predicted positives

![[Pasted image 20231021150448.png]]

What might you use a confusion matrix for?
- Measuring accuracy, precision and recall
- Comparing predicted values with actual values

How is precision defined?
- The proportion of predicted positive values that are actually positive

What would you use to measure the proportion of actual spam messages that are correctly predicted as spam by your classifier?
- Recall

Imagine you are building a spam classifier for incoming email messages.
- What kind of test data would you use to evaluate its performance?
- How would you determine the ground truth (e.g. whether a given message was actually spam or not)?
- What performance metrics would you choose?
- Should you optimize your classifier for precision or recall? Why?


## Example 1

* I would use a validation dataset, ideally with an equal portions of spam and non-spam messages
* as a binary label: spam/not-spam
* I would use both recall and precision, as it's both important to evaluate the performance of this model. _Recall_ will show how many actually spam messages were detected as a spam. Precision will show how many not spam messages falsely detected as a spam.
* I would optimize for a balance of precision and recall.

## Example 2

1. **Test Data Selection**:
- **Random Sampling**: You should use a diverse dataset that represents the types of emails your classifier will encounter. This dataset should include a mix of spam and non-spam (ham) messages.
- **Stratified Sampling**: Ensure that your test data maintains the same proportion of spam and non-spam messages as your real-world email traffic.
1. **Determining Ground Truth**:
- **Manual Labeling**: You would need a labeled dataset where each email message is marked as either spam or not by human annotators. This can be a time-consuming process, but it's crucial for training and evaluating your classifier.
- **Historical Data**: You can use historical data with known labels if available, but it's important to update this dataset over time to account for evolving spam tactics.
2. **Performance Metrics**:
- **Accuracy**: It measures the overall correctness of your classifier. However, accuracy alone might not be the best metric for imbalanced datasets (where spam is much less frequent than non-spam).
- **Precision**: Precision measures the fraction of true positive predictions out of all positive predictions (spam messages predicted as spam). It's crucial when you want to minimize false positives, which can be very annoying for users.
- **Recall**: Recall measures the fraction of true positive predictions out of all actual positives (all spam messages). It's important when missing spam (false negatives) is a significant concern because it can let actual spam through to the inbox.
- **F1-Score**: The F1-score is the harmonic mean of precision and recall and can be useful when you want a balance between the two metrics.
- **ROC Curve and AUC**: Receiver Operating Characteristic (ROC) curves and Area Under the Curve (AUC) provide a graphical representation of your classifier's performance across various thresholds.
3. **Classifier Optimization**:
- Whether to optimize for precision or recall depends on your specific use case and priorities:
- **Optimize for Precision**: If you want to avoid false positives at all costs (i.e., you don't want legitimate emails classified as spam), prioritize precision. This is critical in situations where false positives have severe consequences, such as marking important emails as spam.
- **Optimize for Recall**: If missing spam emails (false negatives) is more problematic, prioritize recall. This is important when users don't want to see any spam in their inbox, even if it means some non-spam messages might be misclassified as spam.

# Text processing

Objectives:
- Understand text processing fundamentals
- Apply text processing techniques
- Manipulate unstructured data

Sources of unstructured data:
- Documents
- Emails
- Social media
- Customer feedback
- Web pages
- Books
- Open-ended survey responses
- Audio and video

Problems:
- Polysemy: One word maps to many concepts
	- e.g. bat
- Synonymy: Once concept maps to many words
	- e.g. smart / bright/ clever
- Word order:
	- Venetian blind vs. blind Venetian
- Language is generative:
	- Starbucks coffee is my favorite /
	- The place I like most to feed my caffeine addiction is ...
- Many different ways to express a given idea:
	- paraphrase, metaphor, idioms
- Changes in languages
	- I want to buy a mobile (cellphone or vehicle)
- Ill-formed input
	- accomodation office (incorrect spelling)
- Co-ordination, negation
	- This is not a talk about neuro-linguistic programming. (we have explicitly said the talk is not about a topic, but a search engine might index it and show it)
- Multi-linguality
	- Claudia Schiffer is on the cover of Elle (the magazine name is in French and the name of the woman is German and the whole sentence makes sense in English)
- Sarcasm, irony, slang, jargon
	I liked it (I actually did not)



Drunk gets nine years in violin case
Stolen painting found by tree
Deer kill 300,000



The sentences are ambiguous at the sentence level.
(To determine structure and the correct intent, we must solve ambiguity)

Ambiguity works at many levels:
- Lexical analysis (tokenisation)
	- The cat sat on the mat
	- I can't tokenise this sentence (is 'can't' one or two tokens)
- Stop word removal: not every word conveys the same amount of information
	- The Who, the and, with that
	- To be or not to be (when analyzing Shakespeare these tokens shouldn't be eliminated)
- Stemming
	- fishing, fished, fish, fisher --> fish (the stem)
	- argue, argued, argues, arguing --> argu
- Lemmatization
	- Linguistically principled analysis (syntactic category)
		- Passing --> pass + ING
		- Were --> be (lemma) + PAST
		- Delegate --> de-leg-ate (?)
- Morphology (shape: prefixes, suffixes)

Grouping together the inflected forms of a word so they can be analysed as a single item is known as lemmatisation.


Ambiguity:

- Syntax (part of speech tagging)
	- noun, pronoun, adjective, determiner, verb, adverb, preposition, conjunction, interjection
	- book -> NOUN, VERB
	- that -> DETERMINER
	- flight -> NOUN
	- Book that flight -> VERB DET NOUN

The ambiguity:
- Time flies like an arrow -> NOUN VERB PREP DET NOUN
- Fruit flies like a banana -> ? 

- Parsing (grammar)
	- I saw a Venetian blind
	- I saw a blind Venetian
	- I saw the man on the hill with a telescope (who is holding the telescope?)

Sentence boundary detection
- Does punctuation denote the end of a sentence?
- "But not always!", said Fred...



The ambiguity in the sentence ‘Fruit flies like a banana’ is primarily at what level?
That’s right, this sentence is syntactically ambiguous


Syntactic parsing uses rules of:

No, morphology refers to the internal structure of tokens
No, tokenisation is the process of splitting a text into smaller units such as words
That’s right, syntactic parsing uses rules of grammar
No, lemmatisation is a form of word normalisation





That’s right, sentence segmentation is a way of tokenizing a text into individual sentences


Stemming is a more crude, heuristic process
Lemmatisation is informed by the linguistic context



The study of systematic differences between language genres is known as:
That’s right, stylistics is a type of linguistic inquiry




Which of the following are common ways to structure a text corpus?

1 / 1 point

Isolated

Correct

That’s right, Gutenberg is an example of an isolated text corpus

Categorised

Correct

That’s right, Brown is an example of a categorised text corpus

Overlapping

Correct
That’s right, Reuters is an example of an overlapping categorised text corpus


# Language modeling

Objectives:
- Prediction and generation
- Perform basic statistical analyses
- Understand how to statistically model natural language
- Perform topic modelling

Simple statistics:




Large collections of text data are known as corpora.
Text data can be analysed using frequency distributions.
Text samples can be generated as a sequence of bigrams.


## Probabilistic language models

How likely is a given sequence of words?

Machine translation:
- Strong tea vs powerful tea
- Strong engine vs powerful engine

Speech recognition:
- I can *recognize* speech
- I can *wreck a nice* beach

Computing probabilities:

P(W) = P(w1, w2, w3, ..., wn)

Compute probability of an upcoming term:

P(w5 | w1, w2, w3, w4)

Chain rule:

P(x1, x2, x3, x4) = P(x1) P(x2 | x1) P(x3 | x1, x2) ...

P(mat | the cat sat on the) = count(the cat sat on the mat) / count(the cat sat on the) = 8 / 10 = 0.8

Can't estimate all sequences from finite training data.

P(bed | the cat sat on the)

However, we did not find any occurrence of 'the cat sat on the bed' in our corpus, and as a result:

0 / 10 = 0.0? (this is wrong)


We don't predict on the entire history, we use a much more limited fragment, the most immediate fragment.

Second order Markov model:
P(mat | the cat sat on the) = P(mat | on the)

What is the key idea behind the Markov assumption?
The current state depends on only a finite fixed number of previous states