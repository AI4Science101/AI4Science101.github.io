---
title: CRISPR Repair Outcome Prediction
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: single_pred_menu
hide_hero: true
---

# CRISPR Repair Outcome Prediction Task Overview


<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
CRISPR-Cas9 is a gene editing technology that allows targeted deletion or modification of specific regions of the DNA within an organism. This is achieved through designing a guide RNA sequence that binds upstream of the target site which is then cleaved through a Cas9-mediated double stranded DNA break. The cell responds by employing DNA repair mechanisms (such as non-homologous end joining) that result in heterogeneous outcomes including gene insertion or deletion mutations (indels) of varying lengths and frequencies. This task aims to predict the repair outcome given a DNA sequence.
</p>

<p class="is-size-6"> <strong> Impact: </strong>  
Gene editing offers a powerful new avenue of research for tackling intractable illnesses that are infeasible to treat using conventional approaches. For example, the FDA recently approved engineering of T-cells using gene editing to treat patients with acute lymphoblastic leukemia. However, since many human genetic variants associated with disease arise from insertions and deletions, it is critical to be able to better predict gene editing outcomes to ensure efficacy and avoid unwanted pathogenic mutations.
</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
The distribution of Cas9-mediated editing products at a given target site is reproducible and dependent on local sequence context. Thus, it is expected that repair outcomes predicted using well-trained models should be able to generalize across cell lines and reagent delivery methods.
</p>

<p class="is-size-6"> <strong> Product: </strong> Cell and gene therapy.</p>

<p class="is-size-6"> <strong> Pipeline: </strong> Efficacy and safety. </p>

</div>

### Leenay et al.

<p class='is-size-6'>  <strong> Dataset Description: </strong> Primary T cells are a promising cell type for therapeutic genome editing, as they can be engineered efficiently ex vivo and transferred to patients. This dataset consists of the DNA repair outcomes of CRISPR-CAS9 knockout experiments on primary CD4+ T cells drawn from 15 donors. For each of the 1,521 unique genomic locations from 553 genes, we provide the 20-nucleotide guide sequence along with the 3-nucletoide PAM sequence. </p>

<p class="is-size-6"> 5 repair outcomes are included for prediction: fraction of indel reads with an insertion, average insertion length, average deletion length, indel diversity, fraction of repair outcomes with a frameshift. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Regression. Given a DNA sequence, predict the repair outcomes of a CRISPR-CAS9 knockout experiment. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 1,521 DNA sequences (guide+PAM) with 5 repair outcomes for each measured across different donor populations of primary T cells. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

To obtain the label names, 

```python
from tdc.utils import retrieve_label_name_list
label_list = retrieve_label_name_list('Leenay')
```

Then, proceed with the usual data loader:

``` python
from tdc.single_pred import CRISPROutcome
data = CRISPROutcome(name = 'Leenay', label_name = label_list[0])
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://idp.nature.com/authorize/casa?redirect_uri=https://www.nature.com/articles/s41587-019-0203-2&casa_token=nIKOlfHR0fkAAAAA:LspabShsQSiLsP0z4vu0xYJWwIOWLbWfKBTwIwNgEFNuSan3vxMKI133KNyMTB6onOYHAS7Ql27lkl4_Og">[1] Leenay, Ryan T., et al. "Large dataset enables prediction of repair after CRISPR–Cas9 editing in primary T cells." Nature biotechnology 37.9 (2019): 1034-1037.</a> 

<p class='is-size-6'> <strong> Dataset License: </strong><a href="https://creativecommons.org/licenses/by/3.0/">CC BY 3.0</a>.</p>

<hr />