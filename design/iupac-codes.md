# IUPAC Codes

## IUPAC Nucleotide Code

| IUPAC nucleotide code | Base                |
| --------------------- | ------------------- |
| A                     | Adenine             |
| C                     | Cytosine            |
| G                     | Guanine             |
| T (or U)              | Thymine (or Uracil) |
| R                     | A or G              |
| Y                     | C or T              |
| S                     | G or C              |
| W                     | A or T              |
| K                     | G or T              |
| M                     | A or C              |
| B                     | C or G or T         |
| D                     | A or G or T         |
| H                     | A or C or T         |
| V                     | A or C or G         |
| N                     | any base            |

## IUPAC Amino Acid Code

| IUPAC amino acid code | Three letter code | Amino acid    |
| --------------------- | ----------------- | ------------- |
| A                     | Ala               | Alanine       |
| C                     | Cys               | Cysteine      |
| D                     | Asp               | Aspartic Acid |
| E                     | Glu               | Glutamic Acid |
| F                     | Phe               | Phenylalanine |
| G                     | Gly               | Glycine       |
| H                     | His               | Histidine     |
| I                     | Ile               | Isoleucine    |
| K                     | Lys               | Lysine        |
| L                     | Leu               | Leucine       |
| M                     | Met               | Methionine    |
| N                     | Asn               | Asparagine    |
| P                     | Pro               | Proline       |
| Q                     | Gln               | Glutamine     |
| R                     | Arg               | Arginine      |
| S                     | Ser               | Serine        |
| T                     | Thr               | Threonine     |
| V                     | Val               | Valine        |
| W                     | Trp               | Tryptophan    |
| Y                     | Tyr               | Tyrosine      |

## RNA Structural Constraint Notation

| symbol | meaning                                                         |
| ------ | --------------------------------------------------------------- |
| (      | nucleotide must be base paired (upstream)                       |
| )      | nucleotide must be base paired (downstream, paired to upstream) |
| .      | no constraint, nucleotide may/may not be base paired            |
| x      | nucleotide may not be base paired                               |

### Examples

#### An RNA hairpin containing a 5-nucleotide duplex and a 4-nucleotide hairpin loop.

```
(((((xxxx)))))
```

#### An RNA hairpin containing a 5-nucleotide duplex, an essential internal loop, and a 6-nucleotide hairpin loop.

```
(((x((xxxxxx))x)))
```

#### An RNA cloverleaf containing 3 branches and assorted bulges, internal loops, and hairpin loops. Some are essential and others not.

```
(((((xx(((((..xx..((((((.xxx.))).)))xx(((xx((..xxxx..))xx))).....((x(((((((.xxx.)))))))))xxxx))))))))))...
```

