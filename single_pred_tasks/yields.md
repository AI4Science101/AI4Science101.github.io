---
title: Reaction Yields Prediction
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: single_pred_menu
hide_hero: true
---

# Reaction Yields Prediction Task Overview


<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
Vast majority of small-molecule drugs are synthesized through chemical reactions. Many factors during reactions could lead to suboptimal reactants-products conversion rate, i.e. yields. Formally, it is defined as the percentage of the reactants successfully converted to the target product. This learning task aims to predict the yield of a given single chemical reaction.
</p>

<p class="is-size-6"> <strong> Impact: </strong>  
To maximize the synthesis efficiency of interested products, an accurate prediction of the reaction yield could help chemists to plan ahead and switch to alternate reaction routes, by which avoiding investing hours and materials in wet-lab experiments and reducing the number of attempts.
</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
The models are expected to extrapolate to unseen reactions with diverse chemical structures and reaction types. 
</p>

<p class="is-size-6"> <strong> Product: </strong> Small-molecule. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Manufacturing - Synthesis planning. </p>

</div>

### Buchwald-Hartwig

<p class='is-size-6'>  <strong> Dataset Description: </strong> Ahneman et al. performed high-throughput experiments on Pd-catalysed Buchwald–Hartwig C-N cross coupling reactions, measuring the yields for each reaction. </p>

<p class='is-size-6'>  <strong> Task Description: </strong> Given reactant and product set X, predict the yields Y. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 55,370 reactions. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.single_pred import Yields
data = Yields(name = 'Buchwald-Hartwig')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://www.sciencedirect.com/science/article/pii/S2451929420300851">[1] Sandfort et al. "A structure-based platform for predicting chemical reactivity." Chem (2020). </a> 

<a href="https://science.sciencemag.org/content/360/6385/186.abstract?casa_token=Y1YYm8zLW4YAAAAA:U2B1Mqw-wjgZuqf2jd5eDUSmOCHm9dKMIqrMR5aGs4Js6eCwXV4gGPvA95wgqF-Gf6UjomO9FaAFeJQ"> [2] Ahneman et al. "Predicting reaction performance in C–N cross-coupling using machine learning." Science 360.6385 (2018): 186-190.
</a>

<a href="https://chemrxiv.org/ndownloader/files/25011413"> [3] Schwaller, Philippe, et al. "Prediction of Chemical Reaction Yields using Deep Learning." (2020). ChemRxiv.</a>

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>


<hr />


### USPTO

<p class='is-size-6'>  <strong> Dataset Description: </strong> TDC parses the yields outcome from the full USPTO (United States Patent and Trademark Office) dataset. </p>

<p class='is-size-6'>  <strong> Task Description: </strong> Given reactant and product set X, predict the yields Y. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 853,638 reactions. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.single_pred import Yields
data = Yields(name = 'USPTO_Yields')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://aspace.repository.cam.ac.uk/handle/1810/244727">[1] Lowe, Daniel Mark. Extraction of chemical structures and reactions from the literature. Diss. University of Cambridge, 2012. </a> 

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/share-your-work/public-domain/cc0/">CC0</a>.</p>


<hr />
