---
title: Gene-Disease Association
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: multi_pred_menu
hide_hero: true
---

# Gene-Disease Association Prediction Task Overview


<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 

Many diseases are driven by genes aberrations. Gene-disease associations (GDA) quantify the relation among a pair of gene and disease. The GDA is usually constructed as a network where we can probe the gene-disease mechanisms by taking into account multiple genes and diseases factors. This task is to predict the association of any gene and disease from both a biochemical modeling and network edge classification perspectives.

</p>

<p class="is-size-6"> <strong> Impact: </strong>  
A high association between a gene and disease could hint at a potential therapeutics target for the disease. Thus, to fill in the vastly incomplete GDA using machine learning accurately could bring numerous therapeutic opportunities. 
</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
Extrapolating to unseen gene and disease pairs with accurate association prediction.
</p>

<p class="is-size-6"> <strong> Product: </strong>  Any therapeutics. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Basic biomedical research, target discovery.  </p>

</div>

### DisGeNET

<p class='is-size-6'>  <strong> Dataset Description: </strong> DisGeNET is a discovery platform containing one of the largest publicly available collections of genes and variants associated to human diseases. DisGeNET integrates data from expert curated repositories, GWAS catalogues, animal models and the scientific literature. DisGeNET data are homogeneously annotated with controlled vocabularies and community-driven ontologies. TDC uses the curated subset from UNIPROT, CGI, ClinGen, Genomics England, CTD (human subset), PsyGeNET, and Orphanet. TDC maps disease ID to disease definition through MedGen and maps GeneID to uniprot amino acid sequence. </p>

<p class='is-size-6'>  <strong> Task Description: </strong> Regression. Given the disease description and the amino acid sequence of the gene, predict their association. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 52,476 gene-disease pairs, 7,399 genes, 7,095 diseases </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.multi_pred import GDA
data = GDA(name = 'DisGeNET')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://academic.oup.com/nar/article-abstract/48/D1/D845/5611674">[1] Piñero, Janet, et al. "The DisGeNET knowledge platform for disease genomics: 2019 update." Nucleic acids research 48.D1 (2020): D845-D855.
</a> 

<a href="https://www.ncbi.nlm.nih.gov/books/NBK159970/?report=printable">[2] Halavi, Maryam, et al. "MedGen." The NCBI Handbook [Internet]. 2nd edition. National Center for Biotechnology Information (US), 2018.</a> 

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/licenses/by-nc-sa/4.0/">CC BY-NC-SA 4.0</a>.</p>


<hr />