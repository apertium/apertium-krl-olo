
# apertium-olo-krl: Karelian krl–Karelian olo rules for rule-based machine translation

This is a visualisation of some rules in apertium transfer.


## Categories (parts of chunks)
   
These are the categories Apertium is using in order to chunk, re-order and
transfer lexemes.
    
| Category | Items |
|:---------|:------|
| noun |  `<n.*>`  `<np.*>`  |
| adj |  `<adj.*>`  |
| verb |  `<vblex.*>`  `<vaux.*>`  `<vbmod.*>`  `<vbser.*>`  |
| sent |  `<sent>`  |

    
## Attributes

These are the morphological analysis value (tag) sets that can be processed in
the transfer.

| Attribute set name | Tags |
|:-------------------|:-----|
| a_case | `<nom>` `<ine>` `<ela>` `<ill>` `<ade>` `<abl>` `<all>` `<par>` `<gen>` `<acc>` `<tra>` `<lat>` `<ess>` `<dat>`  |
| a_noun | `<n>` `<np>`  |
| a_adj | `<adj>`  |
| a_gender | `<m>` `<f>` `<nt>` `<mf>`  |
| a_number | `<sg>` `<pl>` `<sp>`  |
| a_verb | `<vblex>` `<vblex.neg>` `<vaux>` `<vbser>` `<vbmod>`  |
| a_voice | `<actv>` `<pasv>`  |
| a_tense | `<pri>` `<pii>` `<ifi>` `<pres>` `<past>`  |
| a_prsnum | `<p1.sg>` `<p2.sg>` `<p3.sg>` `<p1.pl>` `<p2.pl>` `<p3.pl>`  |

    
## Macros

Macros are helper functions in apertium transfer files.



### test

Parametres: 1

1. **let** `$number` ≔ ""

### case-mangler

Parametres: 1


1. **if** `sl[1]['a_case']`  ≟ `<ela>``sl[1]['a_case']`  ≟ `<ill>``sl[1]['a_case']`  ≟ `<abl>``sl[1]['a_case']`  ≟ `<all>``sl[1]['a_case']`  ≟ `<par>``sl[1]['a_case']`  ≟ `<acc>` **then**:
  1. **let** `tl[1]['a_case']`  ≔ `<acc>`
1. **elseif** `sl[1]['a_case']`  ≟ `<ine>``sl[1]['a_case']`  ≟ `<ade>` **then**:
  1. **let** `tl[1]['a_case']`  ≔ `<dat>`
1. **elseif** `sl[1]['a_case']`  ≟ `<ins>``sl[1]['a_case']`  ≟ `<tra>``sl[1]['a_case']`  ≟ `<ess>` **then**:
  1. **let** `tl[1]['a_case']`  ≔ `<nom>`

### tensemood-mangler

Parametres: 1


1. **if** `sl[1]['a_tense']`  ≟ `<past>` **then**:
  1. **let** `tl[1]['a_tense']`  ≔ `<pii>`

## Rules
    
The actual rules concerning stuff.



### Drop voice from verbs, mangle tense mood
    
#### Matching pattern:
    

1. verb

#### Action:
    

1. tensemood-mangler($1)
1. Output: 
  1. vp``<VP>``
    1. `tl[1]['lem']` `tl[1]['a_verb']` `tl[1]['a_tense']` `tl[1]['a_prsnum']` 
    

### Mangle case of nouns
    
#### Matching pattern:
    

1. noun

#### Action:
    

1. case-mangler($1)
1. Output: 
  1. np``<NP>``
    1. `tl[1]['lem']` `tl[1]['a_noun']` `tl[1]['a_gender']` `tl[1]['a_number']` `tl[1]['a_case']` 
    

### Mangle case of adjs
    
#### Matching pattern:
    

1. adj

#### Action:
    

1. case-mangler($1)
1. Output: 
  1. np``<AP>``
    1. `tl[1]['lem']` `tl[1]['a_adj']` `<sint.attr>`
    

### Default rule
    
#### Matching pattern:
    

1. sent

#### Action:
    

1. Output: 
  1. sent``<SENT>``
    1. `tl[1]['whole']` 
    

- - -

Documentation for [apertium-olo-krl](//github.com/apertium/apertium-olo-krl/).
Generated with [Flammie’s apevis-xslt](https://github.com/flammie/apevis-xslt).
  