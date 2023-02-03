---
title: Developability
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: single_pred_menu
hide_hero: true
---

# Antibody Developability Prediction Task Overview

<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
Immunogenicity, instability, self-association, high viscosity, polyspecificity, or poor expression can all preclude an antibody from becoming a therapeutic. Early identification of these negative characteristics is essential. This task is to predict the developability from the amino acid sequences.
</p>

<p class="is-size-6"> <strong> Impact: </strong>  
A fast and reliable developability predictor can accelerate the antibody development by reducing wet-lab experiments. They can also alert the chemists to foresee potential efficacy and safety concerns and provide signals for modifications. Previous works have devised accurate developability index based on 3D structures of antibody. However, 3D information are expensive to acquire. A machine learning that can calculate developability based on sequence information is thus highly ideal. 
</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
The model is expected to be generalized to unseen classes of antibodies with various structural and functional characteristics.
</p>

<p class="is-size-6"> <strong> Product: </strong> Antibody. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Efficacy and safety. </p>

</div>

### TAP

<p class='is-size-6'>  <strong> Dataset Description: </strong> Immunogenicity, instability, self-association, high viscosity, polyspecificity, or poor expression can all preclude an antibody from becoming a therapeutic. Early identification of these negative characteristics is essential. Akin to the Lipinski guidelines, which measure druglikeness in small molecules, Therapeutic Antibody Profiler (TAP) highlights antibodies that possess characteristics that are rare/unseen in clinical-stage mAb therapeutics. In this dataset, TDC includes five metrics measuring developability of an antibody: CDR length, patches of surface hydrophobicity (PSH), patches of positive charge (PPC), patches of negative charge (PNC), structural Fv charge symmetry parameter (SFvCSP). </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Regression. Given the antibody's heavy chain and light chain sequence, predict its developability. The input X is a list of two sequences where the first is the heavy chain and the second light chain.</p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 242 antibodies. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

<p class='is-size-6'>  <strong> Note: </strong> TAP contains five developability metrics. To retrieve the specific labels for that metric, specify the label name in the <code>label_name</code> variable to the data loader. You can find all available label names by calling: </p>

```python
from tdc.utils import retrieve_label_name_list
label_list = retrieve_label_name_list('TAP')
```

<p class="is-size-6"> Then, go to the standard TDC data loader procedure with the label name specified. </p>

``` python
from tdc.single_pred import Develop
data = Develop(name = 'TAP', label_name = label_list[0])
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://www.pnas.org/content/116/10/4025.short">[1] Raybould, Matthew IJ, et al. "Five computational developability guidelines for therapeutic antibody profiling." Proceedings of the National Academy of Sciences 116.10 (2019): 4025-4030.</a> 

<p class='is-size-6'> <strong> Dataset License: </strong>  <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr />


### SAbDab, Chen et al.

<p class='is-size-6'>  <strong> Dataset Description: </strong> Antibody data from Chen et al, where they process from the SAbDab. From an initial dataset of 3816 antibodies, they retained 2426 antibodies that satisfy the following criteria: 1. have both sequence (FASTA) and Protein Data Bank (PDB) structure files, 2. contain both a heavy chain and a light chain, and 3. have crystal structures with resolution < 3 Å. The DI label is derived from BIOVIA's pipelines.  </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Binary classification. Given the antibody's heavy chain and light chain sequence, predict its developability. The input X is a list of two sequences where the first is the heavy chain and the second light chain.</p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 2,409 antibodies. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.single_pred import Develop
data = Develop(name = 'SAbDab_Chen')
split = data.get_split()
```

<p class='is-size-6'>  <strong> Note: </strong> Since <code>0.3.7</code>, TDC now supports graphein protein representation for this task. To obtain protein representation, see a tutorial <a href="https://github.com/mims-harvard/TDC/blob/main/tutorials/graphein_demo_developability.ipynb"> here! </a> </p>



<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://www.biorxiv.org/content/10.1101/2020.06.18.159798v1.abstract">[1] Chen, Xingyao, et al. "Predicting antibody developability from sequence using machine learning." bioRxiv (2020).
</a> 

<a href="https://academic.oup.com/nar/article-abstract/42/D1/D1140/1044118">[2] Dunbar, James, et al. "SAbDab: the structural antibody database." Nucleic acids research 42.D1 (2014): D1140-D1146.
</a> 

<a href="">[3] Biovia, Dassault Systèmes. "BIOVIA pipeline pilot." Dassault Systèmes: San Diego, BW, Release (2017).
</a> 

<p class='is-size-6'> <strong> Dataset License: </strong>  <a href="https://creativecommons.org/licenses/by/3.0/">CC BY 3.0</a>.</p>

<hr />