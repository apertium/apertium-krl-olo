
# apertium-olo-krl: Karelian krl–Karelian olo rules for rule-based machine translation

This is a visualisation of some rules in apertium transfer.


## Categories (parts of chunks)
   
These are the categories Apertium is using in order to chunk, re-order and
transfer lexemes.
    
| Category | Items |
|:---------|:------|
| SN |  `<SN>`  `<SN.*>`  |

    
## Attributes

These are the morphological analysis value (tag) sets that can be processed in
the transfer.

| Attribute set name | Tags |
|:-------------------|:-----|
| a_nbr | `<sg>`  |

    
## Macros

Macros are helper functions in apertium transfer files.



### test1

Parametres: 1

1. **let** `$number` ≔ ""

## Rules
    
The actual rules concerning stuff.



### REGLA: SN
    
#### Matching pattern:
    

1. SN

#### Action:
    

1. Output: 
  1. ``
    

- - -

Documentation for [apertium-olo-krl](//github.com/apertium/apertium-olo-krl/).
Generated with [Flammie’s apevis-xslt](https://github.com/flammie/apevis-xslt).
  