# snorkel-testing

These notebooks explore `snorkel` (https://github.com/HazyResearch/snorkel), a tool for creating probabilistic labels using a set of heuristics ("labeling functions") in cases where you don't have sufficient training data. This works best with deep learning approaches that accept probabilistic labels as inputs, but here I collapse the probabilities down to flat labels and use simpler `sklearn` approaches so that the notebooks run more quickly. 

The notebooks use labeled datasets, so that we can compare snorkel's performance to performance when using actual labels with the same modeling approaches.

- `snorkel_testing_english_1.ipynb` - Classifying whether a terrorist incident was a suicide attack based on a short text summary. This is a good place to start if you're not familiar with snorkel, because it is a simple usecase and includes some explanation and tips on usage. 96% accuracy using SVM with tf-idf vectorizer. 
- `snorkel_testing_english_2_sarcasm.ipynb` - Classifying whether a Reddit post is sarcastic. Includes implementation of snorkel's transformation functions to augment training data, which in this case did not significantly improve results. 51.8% accuracy using snorkel's label model, 1% increase in accuracy using transformation functions.
- `snorkel_testing_arabic_1_cleaning.ipynb` - Cleaning a dataset of Arabic language news articles for use in this project. 
- `snorkel_testing_arabic_2_oil.ipynb` - Classifying news articles about oil markets. 96% accuracy using multinomial naive Bayes with tf-idf vectorizer. 
- `snorkel_testing_arabic_3_syria.ipynb` - Classifying news articles about Syria. 91% accuracy using multinomial naive Bayes with tf-idf vectorizer. 
- `snorkel_testing_arabic_4_multiclass.ipynb` - Multiclass classification using the same Arabic news dataset. Identifies a few areas where snorkel is not (yet?) optimized to handle multiclass learning. 83% accuracy using random forest with tf-idf vectorizer.

Some miscellaneous tips, based on my experience with snorkel so far:
- Remember that snorkel's approach assumes that each individual labeling function has better than random accuracy! So for instance 50% accuracy for binary classification problems.
- A larger number of simple labeling functons are often more effective than a smaller number of complex labeling functions containing the same information. Let the model learn the relationship between the different rules, rather than nesting a set of rules in a single labeling function.
- It can sometimes be effective to have your most accurate labeling function not abstain, so that all your datapoints are labeled at least once, even if this decreases your accuracy.
- Don't worry too much about the potential that your labeling functions might contain overlapping information, especially given the importance of producing a fairly large number of labeling functions.
