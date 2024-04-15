### SummEval: Re-evaluating Summarization Evaluation
---
- [Zotero Select Link](zotero://select/groups/2480461/items/KVZR352P)
- [Zotero URI](https://www.zotero.org/groups/2480461/items/KVZR352P)
- Authors: [[Alexander R. Fabbri]] [[Richard Socher]] [[Dragomir Radev]] 
- Topics: [[nlp_text_summarization]] [[nlp_metrics]] 
- Venue: #arXiv 
- Year: #2021
---
### Major Contributions
- (1) We re-evaluate 14 automatic evaluation metrics in a comprehensive and consistent fashion using outputs from recent neural summarization models along with expert and crowd-sourced human annotations,
- (2) We consistently benchmark 23 recent summarization models using the aforementioned automatic evaluation metrics
- (3) We release aligned summarization model outputs from 23 papers (44 model outputs) published between 2017 and 2019 trained on the CNN/DailyMail dataset to allow for large-scale comparisons of recent summarization models
- (4) We release a toolkit of 14 evaluation metrics with an extensible and unified API to promote the reporting of additional metrics in papers
- (5) We collect and release expert, as well as crowd-sourced, human judgments for 16 model outputs on 100 articles over 4 dimensions to further research into human-correlated evaluation metrics. 
- (6) Code and data associated with this work is available [here](https://github.com/Yale-LILY/SummEval)
---
### Secondary Contribution
---
### Limitations/Future Work
---
### Notes (Try to use backlinks)
- dataset for training summarization models is the CNN/DailyMail corpus (Hermann et al., 2015), originally a question answering task, which was repurposed for summarization
- We examine the performance of several automatic evaluation methods, including ROUGE and its variants, against the performance of expert human annotators.
- **Metrics**
	- *ROUGE* - (Lin, 2004b), (Recall-Oriented Under study for Gisting Evaluation), measures the number of overlapping textual units (n-grams, word sequences) between the generated summary and a set of gold reference summaries
	- *ROUGE-WE* (Ng and Abrecht, 2015) extends ROUGE by using soft lexical matching based on the cosine similarity of Word2Vec
	- *S3* (Peyrard et al., 2017) is a model-based metric that uses previously proposed evaluation metrics, such as ROUGE, JS-divergence, and ROUGE-WE, as input features for predicting the evaluationscore. The model is trained on human judgment datasets from TAC conferences.
	- *BertScore *(Zhang* et al., 2020) [[_2020_BERTScore]] computes similarityscores by aligning generated and reference summaries on a token-level. Token alignments are computed greedily to maximize the cosine similarity between contextualized token embeddings from BERT.
	- *MoverScore* (Zhao et al., 2019) measures the semantic distance between a summary and reference text by making use of the Word Mover’s Distance (Kusner et al., 2015) operating over n-gram embeddings pooled from BERT representations.
	- *Sentence Mover’s Similarity* (SMS) (Clark et al.,2019) extends Word Mover’s Distance to view documents as a bag of sentence embeddings as well as a variation which represents documents as both a bag of sentences and a bag of words
	- *SummaQA* (Scialom et al., 2019) applies a BERT-based question-answering model to answer cloze-style questions using generated summaries. Questions are generated by masking named entities in source documents associated with evaluated summaries. The metric reports both the F1 overlap score and QA-model confidence
	- *BLANC *(Vasilyev et al., 2020) is a reference-less metric which measures the performance gains of a pre-trained language model given access to a document summary while carrying out language understanding tasks on the source document’s text.
	- *SUPERT* (Gao et al., 2020) is a reference-less metric, originally designed for multi-document summarization, which measures the semantic similarity of model outputs with pseudo-reference summaries created by extracting salient sentences from the source documents, using soft token alignment techniques.
	- *BLEU *(Papineni et al., 2002) is a corpus-level precision-focused metric which calculates n-gram overlap between a candidate and reference utterance and includes a brevity penalty. It is the primary evaluation metric for machine translation.
	- *CHRF* (Popovi´c, 2015) calculates character-based n-gram overlap between model outputs and reference documents
	- *METEOR* (Lavie and Agarwal, 2007) computes an alignment between candidate and reference sentences by mapping unigrams in the generated summary to 0 or 1 unigrams in the reference, based on stemming, synonyms, and paraphrastic matches. Precision and recall are computed and reported as a harmonic mean.
	- *CIDEr* (Vedantam et al., 2015) computes {1-4}-gram co-occurrences between the candidate and reference texts, down-weighting common n-grams and calculating cosine similarity between the ngrams of the candidate and reference texts
- Data Statistics: Grusky et al. (2018) define three measures of the extractiveness of a dataset.
	- *Extractive fragment coverage* is the percentage of words in the summary that are from the source article, measuring the extent to which a summary is a derivative of a text. 
	- *Density* is defined as the average length of the extractive fragment to whicheach summary word belongs. 
	- *Compression ratio* is defined as the word ratio between the articles and its summaries 
	- *Coherence* - the collective quality of all sentences
	- *Consistency* - the factual alignment between the summary and the summarized source.
	- *Fluency* - the quality of individual sentences
	- *Relevance* - selection of important content from the source
- We find that pretrained models such as Pegasus, BART, and T5 consistently performed best on most dimensions
- Scores for extractive models highlight the known shortcomings of such approaches, which are lack of coherence of summaries and issues with selecting relevant content.
- Abstractive model ratings show an increasing trend with respect to the date of publication. This is a promising result as it suggests that the quality of models is improving with time.
---