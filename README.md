treebest
========

TreeBeST: Tree Building guided by Species Tree (Ensembl Compara modifications)

This repository holds the necessary changes of [Heng Li's version](https://github.com/lh3/treebest) to run the latest Ensembl Compara pipeline.
Ensembl is **not** the official maintainer of this software.
Pull-requests can still be submitted, but we will only accept them if they
can provide a benefit to Ensembl.

You can find more documentation on SourceForge: (http://treesoft.sourceforge.net/treebest.shtml)

The main new features are:
* new `-s` option in `treebest sdi`, to allow a user-defined species tree. This change is from [Albert Vilella](https://sites.google.com/site/avilella/)
* new `T` node-tag in the NHX output: a bit-field listing the input trees that support the node. This is populated by the _mmerge_ algorithm
* new `-I` option in `treebest nj`, to carry on the `T` tags from the input tree
* new `-Z` option in `treebest best`, to redefine the PhyML variable `MIN_DIFF_LK`. It prevents PhyML from crashing during its computation
* new `-X` option in `treebest best`, to give a higher weight to the likelihood that comes from the reconciliation with the species tree (default 1)
* Species-intersection scores are now also reported as floating-point values under the `DCS` node-tag. The value is between 0 and 1, and displayed with 4 decimals.
* new `-I` option in `treebest best`, to start from the input tree instead of building one

Other changes include:
* bugfixes / tweaks when processing the filtered alignments (TreeBeST includes a Clustal-score-based MSA-filtering step)
* bugfixes / tweaks when merging the trees
* using `double` instead of `float` for floating-point values

## Branches and tags

There is a single branch (master) where all the development goes. The version number stated in the source code (1.9.2) is not maintained.

`ensembl_production_XX` tags are used to refer to the version used for the
production of Ensembl version XX. Due to deployment constraints, these tags
may not include the latest changes of the master branch.
Instead, we provide `ensembl_release_candidate_Y` tags, Y starting from 1, for
the "next" version we will deploy in production.

## Pre-git history

Treebest used to be kept in a Subversion repository at
http://sourceforge.net/p/treesoft/code/HEAD/tree/branches/lh3/ but Heng
Li's GitHub repository (the parent of this repository) has collapsed the
whole history in just 1 commit.

There is a complete import of the Subversion repository at
https://github.com/muffato/treebest . You can attach it to your checkout to
see

```
git remote add history https://github.com/muffato/treebest
git fetch history
git replace --graft 2a4fe3563e09ff069d319c9987ad4354b984b70f f5bbfb5c2e591ae8a176da960fb0d9edc01f1a96
```
This will pretend that the parent of the commit
2a4fe3563e09ff069d319c9987ad4354b984b70f is
f5bbfb5c2e591ae8a176da960fb0d9edc01f1a96. _replace_ references are
understood by all git tools, incl. `git log`.

