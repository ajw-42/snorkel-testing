# snorkel-testing

A series of notebooks where we teach ourselves to use snorkel (https://github.com/HazyResearch/snorkel) and test it against various use cases. We use labeled datasets so that we can better measure snorkel's performance.

In the `joefirsttest` branch:
- Three notebooks attempting to extract the entity responsible for a terrorist incident from a short text summary.

In the `andrewtesting` branch:
- `snorkel_testing_english_1.ipynb` - Classifying whether a terrorist incident was a suicide attack based on a short text summary. Could be a good place to start if you're not familiar with snorkel, because it includes some explanation and tips on usage.
- `snorkel_testing_english_2_sarcasm.ipynb` - Classifying whether a Reddit post is sarcastic. Includes implementation of snorkel's transformation functions to augment training data, which in this case did not significant improve results.
- `snorkel_testing_arabic_1_cleaning.ipynb` - Cleaning a dataset of Arabic language news articles for use in this project. 
- `snorkel_testing_arabic_2_oil.ipynb` - Classifying news articles about oil markets. An example where snorkel works.
- `snorkel_testing_arabic_3_syria.ipynb` - Classifying news articles about Syria. Another example where snorkel works.
- `snorkel_testing_arabic_4_multiclass.ipynb` - Multiclass classification using the same Arabic news dataset. Identifies a few areas where snorkel is not (yet?) optimized to handle mutliclass learning.
