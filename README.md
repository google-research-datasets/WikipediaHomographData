# Homograph disambiguation data

This repository provides labeled data for training homograph disambiguation
models.

[Citations to follow.--kbg@]

## Annotation

Sentences were extracted from English Wikipedia articles. Homograph were
initially labeled for the most likely `WORDID` (as defined below) in context by
a team of three annotators. In the case that all three did not agree on the
`WORDID`, a fourth senior annotator resolved the disagreements.

There are 161 unique homographs and roughly 100 examples per homograph.

## Organization

The files `data/homographs_train.tsv` and `data/homographs_test.tsv` are TSV
files with the following fields:

* `HOMOGRAPH` (string): the homograph word itself
* `WORDID` (string): name of the pronunciation
* `TEXT` (string): text of the example
* `START_INDEX` (integer): the first byte---inclusive--of the target homograph
   in `TEXT`
* `END_INDEX` (integer): the last byte---exclusive---of the target homograph
   in `TEXT`

These two files represent a suggested 90%/10% train/test split stratified by
homograph.

The file `data/wordids.tsv` is a TSV file which maps from the `WORDID` field
above to information used by the annotator: -a short human-readable description
of the `WORDID`, and a transcription of the `WORDID`. Note that neither are 
intended to be authoritative; they are simply to help users distinguish between
the various `WORDID`s for a homograph. The final two fields have some
impressionistic taxonomic information about the nature of the homography itself
intended for use during error analysis. The following fields are present:

* `HOMOGRAPH` (string): the homograph word itself
* `WORDID` (string): name of the pronunciation
* `LABEL` (string): a short human-readable description of the `WORDID`
* `PRONUNCIATION` (string): a phonemic transcription of the `WORDID` in US
  English.
* `HOMOGRAPHY_TYPE` (string): a binary category describing the broad source of
  homography: morphosyntactic derivations from the same lemma, or lexically
  distinct terms.
* `FINE_HOMOGRAPHY_TYPE` (string): a more detailed classification of the above.

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
