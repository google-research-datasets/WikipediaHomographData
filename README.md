# Homograph disambiguation data

This repository provides labeled data for training homograph disambiguation
models, as described in:

Gorman, K., Mazovetskiy, G., and Nikolaev, V. (2018). Improving homograph
disambiguation with machine learning. In Proceedings of LREC, 1349-1352.

If you use this data in a publication, we would appreciate if you cite this
paper.

## Annotation

Sentences were extracted from English Wikipedia articles. Homograph were
initially labeled for the most likely `WORDID` (as defined below) in context by
a team of three annotators. In the case that all three did not agree on the
`WORDID`, a fourth senior annotator resolved the disagreements.

There are 161 unique homographs and roughly 100 examples per homograph.

## Organization

The files `data/homographs_train.tsv` and `data/homographs_test.tsv` are TSV
files with the following fields:

* `homograph`: the homograph word itself
* `wordid`: name of the pronunciation
* `sentence`: text of the example
* `start`: the first byte---inclusive--of the target homograph in
   `sentence`
* `end: the last byte---exclusive---of the target homograph in `sentence`

These two files represent a suggested 90%/10% train/test split stratified by
homograph.

The file `data/wordids.tsv` is a TSV file which maps from the `WORDID` field
above to information used by the annotator: -a short human-readable description
of the `WORDID`, and a transcription of the `WORDID`. Note that neither are 
intended to be authoritative; they are simply to help users distinguish between
the various `WORDID`s for a homograph. The final two fields have some
impressionistic taxonomic information about the nature of the homography itself
intended for use during error analysis. The following fields are present:

* `homograph`: the homograph word itself
* `wordid`: name of the pronunciation
* `label`: a short human-readable description of the `wordid`
* `pronunciation`: a phonemic transcription of the `wordid` in US English.
* `homograph_type`: a binary category describing the broad source of
  homography: morphosyntactic derivations from the same lemma, or lexically
  distinct terms.
* `fine_homography_type`: a more detailed classification of the above.

## Authors

This data was collected by [Kyle Gorman](mailto:kbg@google.com),
[Vitaly Nikolaev](mailto:vitalyn@google.com), and
[Gleb Mazovetskiy](mailto:glebm@google.com), with help from a team of linguists
and annotators.

## License

See `LICENSE`.

## Contributing

See `CONTRIBUTING`.

## Mandatory disclaimer

This is not an official Google product.
