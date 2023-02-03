---
title: Peptide-MHC Binding
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: multi_pred_menu
hide_hero: true
---

# Peptide-MHC Binding Prediction Task Overview


<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
In the human body, T cells monitor the existing peptides and trigger an immune response if the peptide is foreign. To decide whether or not if the peptide is not foreign, it must bound to a major histocompatibility complex (MHC) molecule. Therefore, predicting peptide-MHC binding affinity is pivotal for determining immunogenicity. There are two classes of MHC molecules: MHC Class I and MHC Class II. They are closely related in overall structure but differ in their subunit composition. This task is to predict the binding affinity between the peptide and the pseudo sequence in contact with the peptide representing MHC molecules.
</p>

<p class="is-size-6"> <strong> Impact: </strong>  
Identifying the peptide that can bind to MHC can allow us to engineer peptides-based therapeutics such vaccines and cancer-specific peptides. 

</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
The models are expected to be generalized to unseen peptide-MHC pairs.

</p>

<p class="is-size-6"> <strong> Product: </strong> Immunotherapy. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Activity - peptide design. </p>

</div>

### MHC Class I, IEDB-IMGT, Nielsen et al.

<p class='is-size-6'>  <strong> Dataset Description: </strong> Binding of peptides to MHC class I molecules (MHC-I) is essential for antigen presentation to cytotoxic T-cells. An organized datasets by NetMHCpan for MHC class I collected from IEDB and IMGT/HLA database. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Regression. Given the amino acid sequence of peptide and the pseudo amino acid sequence of MHC, predict the binding affinity. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 185,985 pairs, 43,018 peptides and 150 MHC class 1s </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.multi_pred import PeptideMHC
data = PeptideMHC(name = 'MHC1_IEDB-IMGT_Nielsen')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://genomemedicine.biomedcentral.com/articles/10.1186/s13073-016-0288-x">[1] Nielsen, Morten, and Massimo Andreatta. "NetMHCpan-3.0; improved prediction of binding to MHC class I molecules integrating information from multiple receptor and peptide length datasets." Genome medicine 8.1 (2016): 1-9. </a> 

<a href="http://www.iedb.org/home_v3.php">[2] Vita, Randi, et al. "The immune epitope database (IEDB): 2018 update." Nucleic acids research 47.D1 (2019): D339-D343.</a>

<a href="https://www.sciencedirect.com/science/article/pii/S240547121930153X">[3] Zeng, Haoyang, and David K. Gifford. "Quantification of uncertainty in peptide-MHC binding prediction improves high-affinity peptide Selection for therapeutic design." Cell systems 9.2 (2019): 159-166.</a>

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr />


### MHC Class II, IEDB, Jensen et al.

<p class='is-size-6'>  <strong> Dataset Description: </strong> Major histocompatibility complex class II (MHC‐II) molecules are found on the surface of antigen‐presenting cells where they present peptides derived from extracellular proteins to T helper cells. Useful to identify T‐cell epitopes. An organized datasets by NetMHCIIpan for MHC class II collected from IEDB database. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Regression. Given the amino acid sequence of peptide and the pseudo amino acid sequence of MHC, predict the binding affinity. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 134,281 pairs, 17,003 peptides and 75 MHC class 2s </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.multi_pred import PeptideMHC
data = PeptideMHC(name = 'MHC2_IEDB_Jensen')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://onlinelibrary.wiley.com/doi/full/10.1111/imm.12889">[1] Jensen, Kamilla Kjaergaard, et al. "Improved methods for predicting peptide binding affinity to MHC class II molecules." Immunology 154.3 (2018): 394-406.</a> 

<a href="http://www.iedb.org/home_v3.php">[2] Vita, Randi, et al. "The immune epitope database (IEDB): 2018 update." Nucleic acids research 47.D1 (2019): D339-D343.</a>

<a href="https://www.sciencedirect.com/science/article/pii/S240547121930153X">[3] Zeng, Haoyang, and David K. Gifford. "Quantification of uncertainty in peptide-MHC binding prediction improves high-affinity peptide Selection for therapeutic design." Cell systems 9.2 (2019): 159-166.</a>

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr />
