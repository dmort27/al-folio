---
layout: page
title: AlloVera
description: The AlloVera allophone database
img: /assets/img/henandchicks.jpg
---

Contrastive units of speech, phonemes, have different contextual realizations called allophones. For example, the English phoneme /p/ has the allophones [p] as in _spit_ and [pʰ] as in _pit_. The relationship between allophone and phone is language specific. For example, in Mandarin Chinese, the phoneme /p/ includes only [p] but in American English, /p/ includes [p] and [pʰ]. [AlloVera](http://github.com/dmort27/allovera) is a resource that provides phoneme to allophone mappings for multiple languages. This database serves as one of the basis of the Allosaurus phone recognition system, a universal speech recognizer that can phonetically transcribe speech with no in-language training data.

AlloVera was used in training [Allosaurus](https://github.com/xinjli/allosaurus), a pretrained universal phone recognizer for more than 2000 languages. For more information, read [the Allosaurus paper](https://arxiv.org/pdf/2002.11800.pdf).

If you use AlloVera in published or other research, please cite the following [paper](https://www.aclweb.org/anthology/2020.lrec-1.656.pdf):

```
@inproceedings{mortensen2020allovera,
    title = "{A}llo{V}era: A Multilingual Allophone Database",
    author = "Mortensen, David R.  and
      Li, Xinjian  and
      Littell, Patrick  and
      Michaud, Alexis  and
      Rijhwani, Shruti  and
      Anastasopoulos, Antonios  and
      Black, Alan W  and
      Metze, Florian  and
      Neubig, Graham",
    booktitle = "Proceedings of the 12th Language Resources and Evaluation Conference",
    month = may,
    year = "2020",
    address = "Marseille, France",
    publisher = "European Language Resources Association",
    url = "https://www.aclweb.org/anthology/2020.lrec-1.656",
    pages = "5329--5336",
    language = "English",
    ISBN = "979-10-95546-34-4",
}
```