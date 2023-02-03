---
title: miRNA-Target Interaction
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: multi_pred_menu
hide_hero: true
---

# MicroRNA-Target Interaction Prediction Task Overview


<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
MicroRNA (miRNA) is small noncoding RNA that plays an important role in regulating biological processes such as cell proliferation, cell differentiation and so on. They usually function to downregulate gene targets. This task is to predict the interaction activity between miRNA and the gene target.
</p>

<p class="is-size-6"> <strong> Impact: </strong>  
Accurately predicting the unknown interaction between miRNA and target can lead to a more complete knowledge about disease mechanism and also could result in potential disease target biomarkers. They can also help identify miRNA hits for miRNA therapeutics candidates.
</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
The model needs to learn the biochemicals of miRNA and target proteins so that it can extrapolate to new set of novel miRNAs and targets in various disease groups and tissues.
</p>

<p class="is-size-6"> <strong> Product: </strong> Small-molecule, miRNA therapeutic. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Basic biomedical research, target discovery, activity. </p>

</div>

### miRTarBase

<p class='is-size-6'>  <strong> Dataset Description: </strong> miRTarBase has accumulated more than three hundred and sixty thousand miRNA-target interactions (MTIs), which are collected by manually surveying pertinent literature after NLP of the text systematically to filter research articles related to functional studies of miRNAs. Generally, the collected MTIs are validated experimentally by reporter assay, western blot, microarray and next-generation sequencing experiments. TDC uses miRBase to obtain miRNA mature sequence. </p>

<p class='is-size-6'>  <strong> Task Description: </strong> Binary Classification. Given the miRNA mature sequence and target amino acid sequence, predict their likelihood of interaction. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 400,082 MTI pairs, 3,465 miRNAs, 21,242 targets </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.multi_pred import MTI
data = MTI(name = 'miRTarBase')
split = data.get_split()
```

<p class="is-size-6"> <strong>Note:</strong> The dataset contains only positive pairs. To get the negative samples, you can call: </p>

```python
data = data.neg_sample(frac = 1)
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://academic.oup.com/nar/article-abstract/46/D1/D296/4595852">[1] Chou, Chih-Hung, et al. "miRTarBase update 2018: a resource for experimentally validated microRNA-target interactions." Nucleic acids research 46.D1 (2018): D296-D302.</a> 

<a href="https://academic.oup.com/nar/article-abstract/47/D1/D155/5179337">[2] Kozomara, Ana, Maria Birgaoanu, and Sam Griffiths-Jones. "miRBase: from microRNA sequences to function." Nucleic acids research 47.D1 (2019): D155-D162.</a> 

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr />
