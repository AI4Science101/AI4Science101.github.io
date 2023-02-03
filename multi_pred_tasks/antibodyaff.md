---
title: Antibody-antigen Affinity
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: multi_pred_menu
hide_hero: true
---

# Antibody-antigen Affinity Prediction Task Overview


<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
Antibodies recognize pathogen antigens and destroy them. The activity is measured by their binding affinities. This task is to predict the affinity from the amino acid sequences of both antigen and antibodies. 
</p>

<p class="is-size-6"> <strong> Impact: </strong>  
Compared to small-molecule drugs, antibodies have numerous ideal properties such as minimal adverse effect and also can bind to many "undruggable" targets due to different biochemical mechanisms. Besides, a reliable affinity predictor can help accelerate the antibody development processes by reducing the amount of wet-lab experiments.
</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
The models are expected to extrapolate to unseen classes of antigen and antibody pairs.

</p>

<p class="is-size-6"> <strong> Product: </strong> Antibody, immunotherapy. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Activity. </p>

</div>

### SAbDab

<p class='is-size-6'>  <strong> Dataset Description: </strong> Antibody-antigen affinity measures the efficacy of the antibody to the antigen. Processed from SAbDab dataset, where we only use protein/peptide antigens for sequence compatbility. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Regression. Given the amino acid sequence of antibody and antigen, predict their binding affinity. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 493 pairs, 431 antibodies and 401 antigens.  </p>

<p class='is-size-6'>  <strong> Note: </strong> In the antibody column, each antibody is organized from left to right as heavy chain to light chain. Also, we highly suggest you take the log affinity when making prediction. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.multi_pred import AntibodyAff
data = AntibodyAff(name = 'Protein_SAbDab')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://academic.oup.com/nar/article-abstract/42/D1/D1140/1044118">[1] Dunbar, James, et al. "SAbDab: the structural antibody database." Nucleic acids research 42.D1 (2014): D1140-D1146. </a> 

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/licenses/by/3.0/">CC BY 3.0</a>.</p>


<hr />