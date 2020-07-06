# RRulesParser

![Test](https://github.com/brsynth/RRulesParser/workflows/Test/badge.svg) ![Publish](https://github.com/brsynth/RRulesParser/workflows/Publish/badge.svg)

Reaction Rules Parser. If no input reaction files is provided, retrieves the reaction rules from [RetroRules](https://retrorules.org).

## Input

* **rules-file**: (string) Filename of reaction rules
* **rule-type**: (string) Valid options: retro, forward, all. Return the rules that are in reverse, forward or both direction
* **outdir**: (string) Path where output files will be written
* **diameters**: (integer list) Valid options: 2, 4, 6, 8, 10, 12, 14, 16. The diameter of the rules to return
* **output-format**: (string) Valid options: csv, tar.gz. Format of the returned file

## Ouput

* **output**: (string): Path of the output file. Either a compressed tar.gz (containing a csv) or csv list of reaction rules that are in a RetroPath2.0 friendly format


## Install
### From pip
```sh
[sudo] python -m pip install rrparser
```
### From Conda
```sh
[sudo] conda install -c brsynth rrparser
```

## Use

### Function call from Python code
```python
from rrparser import Parser

outfile = Parser().parse_rules(rule_type,
                               rules_file,
                               diameters,
                               outdir,
                               outfile,
                               output_format)
```

If parameters from CLI have to be parsed, the function `build_args_parser` is available:
```python
from rrparser import build_args_parser

parser = buildparser()
params = parser.parse_args()
```

### Run from CLI
```sh
python -m rrparser \
  [--rules-file <filename>] \
  [--rule-type {all,retro,forward}] \
  [--outdir <folder>] \
  [--outfile <file>] \
  [--diameters {2,4,6,8,10,12,14,16}] \
  [--output-format {csv,tar.gz}]
```


## Authors

* **Thomas Duigou**
* Melchior du Lac
* Joan Hérisson

## License

This project is licensed under the MIT License.

### How to cite RetroRules?
Please cite:

Duigou, Thomas, et al. "RetroRules: a database of reaction rules for engineering biology." Nucleic acids research 47.D1 (2019): D1229-D1235.