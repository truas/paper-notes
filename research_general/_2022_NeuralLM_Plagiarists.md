### Neural Language Models are Effective Plagiarists
---
- [Zotero Select Link](zotero://select/groups/2480461/items/RP5EJ8NS)
- [Zotero URI](https://www.zotero.org/groups/2480461/items/RP5EJ8NS)
- Authors: [[Stella Biderman]] [[(Edward Raff]] 
- Topics: [[nlp_ppd]] [[nlp_lm]]
- Venue: #arXiv
- Year: #2022
---
### Major Contributions
- In this paper we explore whether transformers can be used to solve introductory level programming assignments while bypassing commonly used AI tools to detect plagiarism.
	- 
- 
---
### Secondary Contribution
- To evaluate our success, we have three major criteria: 
	- 1. We wish to obtain code that correctly solves the exercise. 
	- 2. We wish to obtain code that is not flagged by MOSS as suspiciously similar to the original code. 
	- 3. We wish to minimize the amount of human modification necessary to obtain code from raw GPT-J output.
	- GPT-J does not register as plagiarizing by MOSS Out of the correct completions, none of the code generated by GPT-J stood out as potential plagiarisms according to MOSS
---
### Limitations/Future Work
- As noted previously there are many tools that appear to be suitable for use to detect plagiarism but which are primarily marketed for other purposes. In future work we intended to examine how the intended application is explicitly and implicitly embedded in the functionality of document similarity detectors [Johnson, 2022; Birhane et al., 2021], and incorporate analysis of what it means for such a device to be judged as “working” in its planned application context.
- In particular we were unable to identify any literature investigating how people go about using and interacting with language models, and consequentially need to base some of our experimental methodology on conjecture and common sense.
---
### Notes (Try to use backlinks)
- We choose to study MOSS because it is an opensource model representing the state-of-the-art for plagiarism detection and its design has been widely copied by commercial tools [Devore-McDonald and Berger, 2020].
- In our study we show that a modern neural language models can produce valid, or valid with little additional work, solutions to novel questions that have no given solution. The user is then plagiarizing the model itself, rather than a human being. To the best of our knowledge this is the first demonstration of such an ability, and poses new concerns on how to avoid such potential plagiarism
- To evaluate the ability of GPT-J to fool MOSS, we compare how MOSS views code generated by GPT-J with a dataset of plagiarized introductory coding assignments created by Karnalim et al. [2019]. The dataset contains seven programming exercises suitable for an introduction to programming course with accompanying solutions written in Java.
- As GPT-J was trained on mathematics and computer science text that is written in LATEX [Gao et al., 2020], we choose to provide the model with an input prompt written in LATEX.
- GPT-J generates correct solutions with minimal intervention For six of the seven programming exercises, GPT-J can produce a complete solution that requires no editing.
- neither the exercises from Karnalim et al. [2019] nor the code produced by GPT-J in response to the prompts can be found in the training data.
---
