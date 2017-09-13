
# paraphrase.sr - The Serbian Paraphrase Corpus

The Serbian Paraphrase Corpus (ISLRN [192-200-046-033-9](http://www.islrn.org/resources/192-200-046-033-9/)) consists of 1194 pairs of sentences gathered from news sources on the web.
Each sentence pair was manually annotated with a binary score that indicates whether the sentences are semantically similar enough to be considered close paraphrases.

## Corpus construction
paraphrase.sr was created by exploiting the journalistic convention that the first few sentences of a news article usually give a summary of the article's content.
Hence, extracting the starting sentences from the articles that deal with the same subject matter, but are gathered from different news outlets, is a good way of obtaining semantically related sentence pairs.
Different articles about the same news stories were found through www.vesti.rs, a Serbian news aggregator.
Only the top news stories were used, as they have the highest likelihood of being covered by multiple outlets.
This also ensured the topic variability of the collected sentence pairs.
News stories from 2010 and the first seven months of 2011 were used in this process.

The goal during corpus construction was to gather as many true paraphrases as possible, since for each news story there were usually multiple possible sentence pairings, most of them of semantically diverse sentences.
However, while doing so, it was also important to avoid as much as possible the very simple cases of paraphrasing where the high level of sematic similarity is a consequence of a high string similarity.
It was found that the best results are obtained by giving preference to the pairings of sentences of similar lengths that have around 50% of the same words.
If the sentences in a pair have widely different lengths, the chances of them being paraphrases are reduced.
When the sentences contain almost all the same words, they usually represent mere repetitions of one another (possibly with some small, semantically irrelevant inclusion in one of them).
On the other hand, a low number of words appearing in both sentences usually indicates that the sentences were drawn from semantically diverse parts of a news story.

## Corpus annotation
The entire corpus was annotated by a single annotator.
In order to increase annotation consistency a set of scoring criteria was established.
These criteria are described in the [Decision Support Systems paper](http://www.sciencedirect.com/science/article/pii/S0167923613000614) listed in the References section.

A different annotator scored a portion of the corpus (30% of it) later on, in order to measure the inter-annotator agreement and, thereby, the maximal performance of a computer system on the task of semantic textual similarity.
The agreement measured on this portion of the corpus is 78.27%.

## Corpus format
paraphrase.sr is available in two formats:
* As a single file - *[paraphrase.sr.txt](http://github.com/vukbatanovic/paraphrase.sr/blob/master/paraphrase.sr.txt)* - which contains the full 1194 scored sentence pairs, sorted chronologically.
* As a 70/30% randomly shuffled training/test split, which was used in the papers listed in the reference section. The file *[paraphrase.sr.train.txt](http://github.com/vukbatanovic/paraphrase.sr/blob/master/paraphrase.sr.train.txt)* contains the 835 pairs of the training set, while the file *[paraphrase.sr.test.txt](http://github.com/vukbatanovic/paraphrase.sr/blob/master/paraphrase.sr.test.txt)* contains the 359 test set pairs.

All files share the same three-column tab-separated structure - the first column contains the binary scores, while the sentences are in the second and the third column.
The sentences are written in the Serbian Latin script.
All files are UTF-8 encoded.

## Corpus statistics
paraphrase.sr contains 553 sentence pairs deemed to be semantically equivalent (46.31% of the total number), and 641 semantically diverse pairs (53.69% of the total number).
The given training set has 386 semantically equivalent pairs (46.23%) and 449 semantically diverse pairs (53.77%).
The given test set has 167 semantically equivalent pairs (46.52%) and 192 semantically diverse pairs (53.48%).

## References
If you wish to use the Serbian Paraphrase Corpus in your paper or project, please cite:

**[A software system for determining the semantic similarity of short texts in Serbian](http://ieeexplore.ieee.org/document/6143778/)**, Vuk Batanović, Bojan Furlan, Boško Nikolić, in Proceedings of the 19th Telecommunications Forum (TELFOR 2011), pp. 1249-1252, Belgrade, Serbia (2011). *(Paper in Serbian)*

**[Semantic similarity of short texts in languages with a deficient natural language processing support](http://www.sciencedirect.com/science/article/pii/S0167923613000614)**, Bojan Furlan, Vuk Batanović, Boško Nikolić, Decision Support Systems, vol. 55, no. 3, pp. 710-719 (2013).

## License
[Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)](http://creativecommons.org/licenses/by-nc-sa/4.0/)

If you wish to use this dataset in a commercial product, please contact me at: vuk.batanovic / at / student.etf.bg.ac.rs