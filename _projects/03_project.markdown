---
layout: page
title: Mesoamerican Morphology
description: Comp morph for language documentation
img: /assets/img/ferns.jpg
---

Producing large corpora from minority languages that are useful to descriptive and documentary linguists requires morphological analysis—segmentation and glossing. Traditionally, these tasks have been performed by hand by skilled linguists or language experts. The goal of this project is to automate this process, faciliating the creation of much larger corpora with much less human effort. We are developing new methods for performing these tasks, using as our testbed typologically diverse indigenouos languages of Mexico, including Nahuatl and Mixtecan languages.

As part of this project, we have developed `morphotactics`, a Python library for creating morphotactic FSTs (built on [OpenFST](http://www.openfst.org) and [Pynini](http://www.openfst.org/twiki/bin/view/GRM/Pynini)). It is inspired, in some respects, by LEXC (but is pure Python and supports weights). We are currently using it to construct an FST for Nahuatl.