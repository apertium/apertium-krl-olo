
# apertium-krl-olo: Karelian krl–Karelian olo rules for rule-based machine translation

This is a visualisation of some rules in apertium transfer.


## Categories (parts of chunks)
   
These are the categories Apertium is using in order to chunk, re-order and
transfer lexemes.
    
| Category | Items |
|:---------|:------|
| sent |  `<sent>`  |

    
## Attributes

These are the morphological analysis value (tag) sets that can be processed in
the transfer.

| Attribute set name | Tags |
|:-------------------|:-----|
| a_case | `<nom>` `<gen>` `<acc>` `<dat>` `<ine>` `<ela>` `<ill>` `<ade>` `<abl>` `<all>` `<par>` `<tra>` `<cmp>` `<lat>`  |
| a_verb | `<vblex>` `<vblex.neg>` `<vbser>` `<vbmod>` `<vaux>`  |
| a_tense | `<prs>` `<pis>` `<pri>` `<pii>` `<past>`  |
| a_adj | `<adj>` `<num.ord>`  |
| a_comp | `<pos>` `<comp>` `<sup>`  |
| a_adp | `<post>` `<pr>`  |
| a_adv | `<adv>`  |
| a_noun | `<n>` `<n.acr>` `<np.ant>` `<np.top>` `<np.al>` `<np>` `<np.acr>` `<np.acr.al>` `<np.top.acr>` `<np.al.acr>` `<np.org>` `<np.cog>` `<num.card>` `<prn>`  |
| a_nominal | `<n.acr>` `<n>` `<np.ant>` `<np.top>` `<np.top.use_blacklist>` `<np.cog>` `<np.org>` `<np.al>` `<np>` `<np.acr>` `<np.acr.al>` `<np.top.acr>` `<np.al.acr>` `<num.card>` `<det>` `<prn>` `<adj.pos>`  |
| a_det | `<n>` `<num.card>` `<prn>` `<adj.pos>` `<adv>`  |
| a_prn | `<prn>`  |
| a_number | `<sg>` `<sp>` `<pl>`  |
| a_perf | `<pp>`  |
| a_pers | `<p1.sg>` `<p2.sg>` `<p3.sg>` `<p1.pl>` `<p2.pl>` `<p3.pl>`  |
| a_numtype | `<card>` `<ord>`  |
| a_num | `<num>` `<num.use_nonstd>`  |
| a_inf | `<inf>` `<ger>`  |
| a_conneg | `<conneg>`  |

    
## Macros

Macros are helper functions in apertium transfer files.



### test

Parametres: 1

1. **let** `$conpart` ≔ ""

## Rules
    
The actual rules concerning stuff.



### REGLA: SENT
    
#### Matching pattern:
    

1. sent

#### Action:
    

1. Output: 
  1. sent``<SENT>``
    1. `tl[1]['whole']` 
    

- - -

Documentation for [apertium-krl-olo](//github.com/apertium/apertium-krl-olo/).
Generated with [Flammie’s apevis-xslt](https://github.com/flammie/apevis-xslt).
  