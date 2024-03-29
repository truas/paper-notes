### A Primer in BERTology: What We Know About How BERT Works
---
- [Zotero Select Link](zotero://select/groups/2480461/items/M2RNYNB9)
- [Zotero URI](https://www.zotero.org/groups/2480461/items/M2RNYNB9)
- Authors: [[Anna Rogers]] [[Anna Rumshisky]]
- Topics: [[nlp_survey]] [[nlp_transformers]]
- Venue: #TACL
- Year: #2020
---
### Major Contributions
 - This paper is the first survey of over 150 studies of the popular [[_2019_BERT]] model
---
### Secondary Contribution
---
### Limitations/Future Work
---
### Notes (Try to use backlinks)
- **Syntatics Knowledge**
	- Lin et al. (2019) showed that [[_2019_BERT]] representations are hierarchical rather than linear
	- Tenney et al. (2019b) and Liu et al. (2019a) also showed that [[_2019_BERT]] embeddings encode information about parts of speech, syntactic chunks, and roles.
	- it seems that syntactic structure is not directly encoded in self-attention weights.
		- However, syntactic information can be recovered from BERT token representations.
	- [[_2019_BERT]] ‘‘naturally’’ learns some syntactic information, although it is not very similar to linguistic annotated resource
	- [[_2019_BERT]] takes subject-predicate agreement into account when performing the cloze task
	- Warstadt et al. (2019) showed that BERT is better able to detect the presence of NPIs - negative polarity items - (e.g., ‘‘ever’’) and the words that allow their use (e.g., ‘‘whether’’) than scope violations.
	- [[_2019_BERT]] does not ‘‘understand’’ negation and is insensitive to malformed input.
		- its predictions were not altered even with shuffled word order truncated sentences, removed subjects and objects (Ettinger, 2019). 
		- This could mean that either BERT’s syntactic knowledge is incomplete, or it does not need to rely on it for solving its tasks
- **Semantic Knowlegde**
	[[_2019_BERT]] struggles with representations of numbers
	- Out-of-the-box [[_2019_BERT]] is surprisingly brittle to named entity replacements
- **Word Knowledge**
	- [[_2019_BERT]] struggles with pragmatic inference and role-based event knowledge (Ettinger, 2019).
	- for some relation types, vanilla [[_2019_BERT]] is competitive withmethods relyingon knowledge bases
	- [[_2019_BERT]] cannot reason based on its world knowledge
		- it ‘‘knows’’ that people can walk into houses, and that houses are big, but it cannot infer that houses are bigger than people.
	- **BERT Emeddings**
		- distilled contextualized embeddings better encode lexical semantic information (i.e., they are better at traditional word-level tasks such as word similarity).
		- two randomwords will on average have a much higher cosine similarity than expected if embeddings were directionally uniform (isotropic).
		- BERT’s contextualized embeddings form distinct clusters corresponding to word senses
		- Mickus et al. (2019) note that the representations of the same word depend on the position of the sentence in which it occurs
			- This is not desirable fromthe linguistic point of view
	- **Self-attention Heads**
		- some BERT heads seem to specialize in certain types of syntactic relations.
		- no single head has the complete syntactic tree information, in line with evidence of partial knowledge of syntax
		- Lin et al. (2019) present evidence that attention weights are weak indicators of subject-verb agreement and reflexive anaphora.
		- **Attention Special Tokens**
			- Kovaleva et al. (2019) show that most self-attention heads do not directly encode any non-trivial linguistic information, at least when fine-tuned on [[GLUE]]
	- **Layers**
			- the lower layers have the most information about linear word order
				- Lin et al. (2019) report a decrease in the knowledge of linear word order around layer 4 in BERT-base
			-  that syntactic information is most prominent in the middle layers of BERT
			-  ‘‘the basic syntactic information appears earlier in the network while high-level semantic features appear at the higher layers
			-  The final layers of BERT are the most task-specific	-  syntactic information appears early in the model and can be localized, semantics is spread across the entire mode
		-  **Training**
			-  the number of heads was not as significant as the number of layers.
			-  All in all, changes in the number of heads and layers appear to perform different function
			-  The consensus in the community is that pre-training does help in most situations, but the degree and its exact contribution requires further investigation
		-  all but a few Transformer heads could be pruned without significant losses in performance.
		-  For instance, BERT has heads that seem to encode frame-semantic relations, but disabling them might not hurt downstream task performance (Kovaleva et al., 2019); this suggests that this knowledge is not actually used
	---
