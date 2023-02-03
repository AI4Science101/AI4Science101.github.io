---
title: Reaction
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: generation_menu
hide_hero: true
---

# Reaction Outcome Prediction Task Overview


<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
Reaction outcome prediction is to predict the reaction products given a set of reactants. Reaction outcome prediction can be seen as reverse process of retrosynthesis prediction. 
</p>

<p class="is-size-6"> <strong> Impact: </strong>  
Predicting the products as a result of a chemical reaction is a fundamental problem in organic chemistry. It is quite challenging for many complex organic reactions. Conventional empirical methods that relies on experimentation requires intensive manual label of an experienced chemist, and are always time-consuming and expensive. Reaction Outcome Prediction aims at automating the process. 
</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
 The model is expected to accurately generate product for novel set of reactants across reaction types with varying reaction conditions.
</p>

<p class="is-size-6"> <strong> Product: </strong> Small-molecule. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Manufacturing - Synthesis planning. </p>

</div>

### USPTO

<p class='is-size-6'>  <strong> Dataset Description: </strong> The full USPTO (United States Patent and Trademark Office) retrosynthesis dataset. </p>

<p class='is-size-6'>  <strong> Task Description: </strong> Given reactant set X, predict the reaction product Y. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 1,939,253 reactions. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.generation import Reaction
data = Reaction(name = 'USPTO')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://figshare.com/articles/Chemical_reactions_from_US_patents_1976-Sep2016_/5104873"> [1]  Daniel Lowe. Chemical reactions from US patents (1976-Sep2016).
</a>

<a href="http://papers.nips.cc/paper/6854-predicting-organic-reaction-outcomes-with-weisfeiler-lehman-network"> [2] Jin, Wengong, et al. "Predicting organic reaction outcomes with weisfeiler-lehman network." NeurIPS. 2017.
</a>

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/share-your-work/public-domain/cc0/">CC0</a>.</p>


<hr />
