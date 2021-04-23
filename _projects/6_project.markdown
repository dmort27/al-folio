---
layout: page
title: Ranking Transfer Languages
description: Pragmatic Features
img: /assets/img/moss.jpg
---

Cross-lingual transfer is by now an established technique for several NLP tasks in low-resource settings. It has also been shown that algorithmic techniques can outperform human judgements in selecting transfer languages. Aside from properties of the datasets, typological features (mostly morphological and syntactic in nature) have been found to be effective in the selection of such languages. However, most of the tasks on which such ranking systems have been evaluated have been “syntax heavy”—they rely heavily on morphosyntactic structure. Such tasks include syntactic parsing and machine translation.

What about “semantics- and pragmatics-heavy” tasks like sentiment analysis, though? Are morphosyntactic features as effective in predicting transferability? Is there a different set of features that could work better? We propose that features which correlate with cultural and pragmatic linguistic behaviors would be better at ranking transfer languages for pragmatically-oriented downstream tasks than the previously-studied typological features.

This hypothesis is explored in our recent EACL paper, “[Cross-Cultural Similarity Features for Cross-Lingual Transfer Learning of Pragmatically Motivated Tasks](https://www.aclweb.org/anthology/2021.eacl-main.204/).” We find that it is, indeed, the case that features like “context-level ratio” and “literal translation quality” are better predictors of transferability for sentiment analysis in a diverse set of languages, but are *worse* predictors of transferability for dependency parsing, than features from morphological and syntactic typology. The BibTeX reference for this paper is as follows:

```
@inproceedings{sun-etal-2021-cross,
    title = "Cross-Cultural Similarity Features for Cross-Lingual Transfer Learning of Pragmatically Motivated Tasks",
    author = "Sun, Jimin  and
      Ahn, Hwijeen  and
      Park, Chan Young  and
      Tsvetkov, Yulia  and
      Mortensen, David R.",
    booktitle = "Proceedings of the 16th Conference of the European Chapter of the Association for Computational Linguistics: Main Volume",
    month = apr,
    year = "2021",
    address = "Online",
    publisher = "Association for Computational Linguistics",
    url = "https://www.aclweb.org/anthology/2021.eacl-main.204",
    pages = "2403--2414",
    abstract = "Much work in cross-lingual transfer learning explored how to select better transfer languages for multilingual tasks, primarily focusing on typological and genealogical similarities between languages. We hypothesize that these measures of linguistic proximity are not enough when working with pragmatically-motivated tasks, such as sentiment analysis. As an alternative, we introduce three linguistic features that capture cross-cultural similarities that manifest in linguistic patterns and quantify distinct aspects of language pragmatics: language context-level, figurative language, and the lexification of emotion concepts. Our analyses show that the proposed pragmatic features do capture cross-cultural similarities and align well with existing work in sociolinguistics and linguistic anthropology. We further corroborate the effectiveness of pragmatically-driven transfer in the downstream task of choosing transfer languages for cross-lingual sentiment analysis.",
}
```

One interesting finding of this paper is that emotional semantic distance (ESD) is a better metric of cultural similarity (better groups languages into cultural areas) than other typological features. When the languages in our sample are grouped based on syntactic and morphological features, the resulting network is as follows:
![Languages Grouped by Morphosyntactic Typology]({{site.baseurl}}/assets/img/syn_network.png)

But when the grouping is based on ESD, a more culturally and geographically intuitive emerges:
![Languages Grouped by Emotional Semantic Distance]({{site.baseurl}}/assets/img/esd_network.png)