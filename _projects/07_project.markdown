---
layout: page
title: URIEL
description: Typological Compendium
img: /assets/img/lichen.jpg
redirect-from:
    - /~dmortens/uriel
---

### Introduction

The URIEL knowledge base is a structured compendium of information on language typology and language universals that was developed as part of DARPA's LORELEI project.

For the most recent version of URIEL and `lang2vec`, use `pip` to install the lang2vec package from PyPI.

Download the newest non-PyPI release [here]({{site.baseurl}}/assets/xz/uriel_lang2vec_latest.tar.xz). Read the README in Markdown.

### Releases

URIEL is currently released with `lang2vec`, a tool for querying it. The development versions of URIEL and lang2vec are available in a GitHub repository. For most users, it will be more convinient to install the `lang2vec` package from PyPI using pip. The latest stand-along release of `lang2vec` is available [here]({{site.baseurl}}/assets/xz/uriel_lang2vec_lastest.tar.xz).

### How to Cite

If you use URIEL in your research, please cite it as follows:

Patrick Littell, David Mortensen, Ke Lin, Katherine Kairis, Carlisle Turner, and Lori Levin (2017). URIEL and lang2vec: Representing languages as typological, geographical, and phylogenetic vectors. Proceedings of the 15th Conference of the European Chapter of the Association for Computational Linguistics: Volume 2, Short Papers, pages 8–14, Valencia, Spain, April 3-7.

The appropriate BibTeX entry is as follows:

```
@InProceedings{littell2017uriel,
  author = "Littell, Patrick
           and Mortensen, David R.
           and Lin, Ke
           and Kairis, Katherine
           and Turner, Carlisle
           and Levin, Lori",
  title = "URIEL and lang2vec: Representing languages as typological, geographical, and phylogenetic vectors",
  booktitle = "Proceedings of the 15th Conference of the European Chapter of the Association for Computational Linguistics: Volume 2, Short Papers",
  year = "2017",
  publisher = "Association for Computational Linguistics",
  pages = "8--14",
  location = "Valencia, Spain",
  url = "http://aclweb.org/anthology/E17-2002"
}
```

### Contributors

URIEL is a product of [LLab](https://llab-cmu.github.io/). The principle contributors are:

* [Patrick Littell](http://littell.nfshost.com/)
* [David R. Mortensen](http://www.lti.cs.cmu.edu/~dmortens/)
* [Lori Levin](http://www.cs.cmu.edu/~lsl/)

### URIEL README

#### URIEL Typological Compendium

This directory represents the result data from the third URIEL Typological Compendium release (v0_2).

##### Features

All CSV files listed here have a simple tabular format, in CSV format, with ISO 639-3 language identifiers in the first column, and features at the top.  All features are in [0.0,1.0] intervals.

For example, the file might look something like:

G_CODE, S_SUBJECT_BEFORE_VERB, S_SUBJECT_AFTER_VERB
deu, 1.0, 0.0
eng, 1.0, 0.0

These files are deduced from feature databases (e.g., WALS, PHOIBLE) and text databases (e.g. Ethnologue).  Each source is given as its own CSV file.

**wals.csv** -- Features derived from the World Atlas of Language Structures.
**sswl.csv** -- Features derived from Syntactic Structures of the World's Languages.
**ethno.csv** -- Features derived from (shallowly) parsing the prose typological descriptions in Ethnologue (Lewis et al. 2015).
**phoible_aa.csv** -- AA = Alphabets of Africa. Features derived from PHOIBLE's normalization of *Systèmes alphabétiques des langues africaines* (Hartell 1993, Chanard 2006).
**phoible_gm.csv** -- GM = Green and Moran.  Features derived from PHOIBLE's normalization of Christopher Green and Steven Moran's pan-African inventory database.
**phoible-ph.csv** -- PH = PHOIBLE.  Features derived from PHOIBLE proper, by Moran, McCloy, and Wright (2012).
**phoible-ra.csv** -- RA = Ramaswami.  Features derived from PHOIBLE's normalization of *Common Linguistic Features in Indian Languages: Phoentics* (Ramaswami 1999).
**phoible-saphon.csv** - SAPHON = South American Phonological Inventory Database.  Features derived from PHOIBLE's normalization of SAPHON (Lev et al. 2012).
**phoible-spa.csv** - SPA = Stanford Phonology Archive.  Features derived from PHOIBLE's normalization of SPA (Crothers et al., 1979).
**phoible-upsid.csv** - UPSID = UCLA Phonological Segment Inventory Database.  Features derived from PHOIBLE's normalization of UPSID (Maddieson 1984, Maddieson and Precoda 1990).

These data are also available in NPZ (Numpy compressed archive) format as **features.npz**.

The data are also available in one table in:

**all_sources** - Every <language> and <source,feature> pair, in one table.  The feature names across the top have the format SOURCE:FEATURE.  For example:

G_CODE, WALS:SVO, WALS:SOV, SSWL:SVO
eng, 1.0, 0.0, 1.0
fra, 1.0, 0.0, 1.0

##### Geodata

**geo.csv** - There is also a file of geodata (broadly construed), consisting of things like the name of the language, its hypothesized place in the language family tree, and a geocoordinate.  These are drawn from the sources above, from Glottolog, and from the ISO 639-3 code.  These data are also available in NPZ format as **geodata.npz**.

For this release, treat information like the "name" of the language as being for internal reference only; they do not represent every possible name associated with an ISO 639-3 code.  To discover a language's code, look it up in Ethnologue, Glottolog, or an ISO 639-3 reference instead.

For models that are expecting scalar magnitudes, rather than text data or a graph of distances between languages, we also provide geodata-like features in [0.0,1.0] intervals (parallel to ordinary URIEL data).

**fam.csv** -- Each feature indicates membership within a language family (like Indo-European) or branch (like Germanic or West Germanic or Ingveonic), each indicated only numerically.  These data are also available in NPZ format as **family_features.npz**.

**geocoords.csv** -- Each feature indicates the distance (expressed as a fraction of the antipodal distance) from a particular point on the earth.  Points are roughly equidistant from each other (using a Fibonacci spiral geocoordinate spacing algorithm), but points that are not near any languages (e.g., many points in the middle of the ocean) are not considered here.  These data are also available in NPZ format as **geocoord_features.npz**.


##### Distances

The distance files represent "driving distance" charts between two languages, for various metrics (e.g., phylogenetic distance), with 0.0 representing identity and 1.0 being as far apart as two languages can be.

code, deu, eng, swe, jpn
deu, 0.0, 0.4, 0.6, 1.0
eng, 0.4, 0.0, 0.6, 1.0
swe, 0.6, 0.6, 0.0, 1.0
jpn, 1.0, 1.0, 1.0, 0.0

Six charts are provided:

**genetic.csv** -- A distance metric derived from the Glottolog hypothesized tree of language, representing the number of steps upward on the tree until the two languages are unified under a single node, divided by the number of branches in between L1 and the root.  (In other words, the percentage of L1's descent not shared by L2.)  This has the advantage of correctly sorting languages by relation even in a tree with wildly different levels of detail between branches and families.  The downside is that this relationship is not commutative, and the numbers do not have any absolute significance.  (E.g., that L1 and L2 are related by "0.4" is not meaningful except in comparison with other relatives of L1;

**geographical.csv** -- The orthodromic ("great circle") distance between the languages on the surface of the earth, divided by the antipodal distance (i.e., diameter/2).

**featural.csv** -- The distance between the vectors defined by the features in the database, as defined as the arccosine of the dot product of the normalized vectors.  When a feature value is unknown in one of the languages, this feature is not used in the calculation.

**syntactic.csv** -- The same as in s_distance, but with vectors defined by the S_ features in the database.

**phonological.csv** -- The same as in s_distance, but with vectors defined by the P_ features in the database.

**inventory.csv** -- The same as in s_distance, but with vectors defined by the I_ features in the database.

These distances are also available in one NPZ file as **distances.npz**.

##### Derived features

We also provide calculated sources, including consensus values (like averages) and predicted values (such as kNN regressions based on phylogenetic or geographical neighbors).

These feature charts are in the same format as the feature charts above, e.g.:

G_CODE, S_SUBJECT_BEFORE_VERB, S_SUBJECT_AFTER_VERB
deu, 1.0, 0.0
eng, 1.0, 0.0

**avg.csv** -- A simple mean of (known) values in the above sources.  That is to say, it is the probability of a feature being 1.0 if a source is chosen at random.  These data are also available in NPZ format as **feature_averages.npz**

**predicted.csv** -- A predicted set of features based on a weighted kNN classification, with a distance consisting of an evenly weighted composite of the genetic and geographical distances in the tables above.  These data are also available in NPZ format as **feature_predictions.npz**.

##### Other features available by request

Two feature sets are defined for convenience (e.g., in running certain sorts of experiments), but which are not automatically included in this distribution because they are both enormous and do not contain meaningful information.

**id.csv** -- For each language (like "eng"), there is a feature "ID_ENG" that is only true for that language.  (This is used in, e.g., neural polyglot models; if a feature set does not outperform when used in addition to this dataset, then probably all it is learning from the data is a "fingerprint" identifying each language.)  These data are also available in NPZ format as **id_features.npz**.

**random.csv** -- This language has the same languages and features as the average and predicted datasets, but assigns values of 0.0 and 1.0 to them completely at random.  These data are also available in NPZ format as **random_features.npz**.

#### Mini-grammars

As an experimental addition to this release, we have derived skeletal "mini-grammars" for each of the languages.  Each rule is accompanied by a status saying whether it comes from a known feature (attested), a known feature in which different sources disagree as to its value (disputed), or whether it the value is not known but the rule is based on its prediction in **feature_predictions.csv**.  For example, that adjectives come before nouns is attested (all sources agree that this is a normal English phenomenon), while adjectives coming after nouns ("the students involved") is "disputed" (the different sources disagree as to whether this is a general fact of English grammar).

label, expansion, status
S, NP VP, attested
N', A N, attested
N', N A, disputed

These grammars should not be used as if they represent the entire grammar of a language, or can reliably divide grammatical sentences from ungrammatical sentences; for this task they would be completely impoverished.  However, they do potentially provide useful hypotheses about the relative ordering of sentential elements, or provide a starter grammar that can be filled out using other sources of information.


#### REFERENCES

-- 2015. CLDR—Unicode Common Locale Data. Mountain View, CA: Unicode Consortium. (Available online at http://cldr.unicode.org/, accessed on 2015-11-05)

-- 2015. ScriptSource. Dallas: SIL International. (Available online at http://scriptsource.org, accessed on 2015-11-05.)

Collins, Chris & Kayne, Richard(eds.) 2011. Syntactic Structures of the World’s Languages. New York: New York University. (Available online at http://sswl.railsplayground.net, Accessed on 2015-11-05.)

Dryer, Matthew S. & Haspelmath, Martin (eds.) 2013. The World Atlas of Language Structures Online. Leipzig: Max Planck Institute for Evolutionary Anthropology. (Available online at http://wals.info, Accessed on 2015-11-05.)

Hammarström, Harald & Forkel, Robert & Haspelmath, Martin & Bank, Sebastian. 2015. Glottolog 2.6. Jena: Max Planck Institute for the Science of Human History. (Available online at http://glottolog.org, Accessed on 2015-11-06.)

Lewis, M. Paul (ed.), 2009. Ethnologue: Languages of the World, Sixteenth edition. Dallas, Texas: SIL International. Online version: http://www.ethnologue.com/16.

Moran, Steven & McCloy, Daniel & Wright, Richard (eds.) 2014. PHOIBLE Online. Leipzig: Max Planck Institute for Evolutionary Anthropology. (Available online at http://phoible.org, Accessed on 2015-11-05.)