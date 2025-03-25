# Basic vocab
Corpus: the whole dataset of text
Document: a specific entry in the dataset


# TF IDF
- Term Frequency   Inverse Document Frequency
- An alternate to using "soft stop words"
	- words that are generic for a specific context, such as "product" or "item" in customer review data
- Rare words and very frequent words are given smaller weights
- For every term, calculate a TF-IDF number
- TF is number of times term appears in doc (typical bag of words count)
- IDF is inverse of the frequency that a term appears across all docs in the corpus
	- IDF is 1 if term appears in all docs #interview_question 
	- otherwise, it will have a weight > 1, increasing as it is *less* frequent across the docs
- Intuition: If a term occurs a lot within a document, it is likely important for describing that documents (TF). If a term occurs a lot within that document relative to within other documents, it is also more important for describing that doc that others. Words that are common across all docs arent as informative
