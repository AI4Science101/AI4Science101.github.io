---
title: Drug Synergy Prediction
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: multi_pred_menu
hide_hero: true
---

# Drug Synergy Prediction Task Overview


<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
Synergy is a dimensionless measure of deviation of an observed drug combination response from the expected effect of non-interaction. Synergy can be calculated using different models such as the Bliss model, Highest Single Agent (HSA), Loewe additivity model and Zero Interaction Potency (ZIP). Another relevant metric is CSS which measures the drug combination sensitivity and is derived using relative IC50 values of compounds and the area under their dose-response curves.
</p>

<p class="is-size-6"> <strong> Impact: </strong>  
Drug combination therapy offers enormous potential for expanding the use of existing drugs and in improving their efficacy. For instance, the simultaneous modulation of multiple targets can address the common mechanisms of drug resistance in the treatment of cancers. However, experimentally exploring the entire space of possible drug combinations is not a feasible task. Computational models that can predict the therapeutic potential of drug combinations can thus be immensely valuable in guiding this exploration.
</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
It is important for model predictions to be able to adapt to varying underlying biology as captured through different cell lines drawn from multiple tissues of origin. Dosage is also an important factor that can impact model generalizability. 

</p>

<p class="is-size-6"> <strong> Product: </strong> Small-molecule. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Activity. </p>

</div>

### OncoPolyPharmacology

<p class='is-size-6'>  <strong> Dataset Description: </strong> A large-scale oncology screen produced by Merck & Co., where each sample consists of two compounds and a cell line. The dataset covers 583 distinct combinations, each tested against 39 human cancer cell lines derived from 7 different tissue types. Pairwise combinations were constructed from 38 diverse anticancer drugs (14 experimental and 24 approved). The synergy score is calculated by Loewe Additivity values using the batch processing mode of Combenefit. The genomic features are from ArrayExpress database (accession number: E-MTAB-3610) and  was quantile normalized and summarized with Factor Analysis for Robust Microarray Summarization (FARMS). The processed data is provided by DeepSynergy. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Regression. Given the gene expression of cell lines and two SMILES strings of the drug combos, predict the drug synergy level. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 23,052 drug combo-cell line points, among 39 cancer cell lines and 37 drugs </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> <span class="tag is-info is-light">Cold Cell Line Split</span> </p>

``` python
from tdc.multi_pred import DrugSyn
data = DrugSyn(name = 'OncoPolyPharmacology')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://mct.aacrjournals.org/content/15/6/1155.short">[1] O'Neil, Jennifer, et al. "An unbiased oncology compound screen to identify novel combination strategies." Molecular cancer therapeutics 15.6 (2016): 1155-1162. </a> 

<a href="https://academic.oup.com/bioinformatics/article-abstract/34/9/1538/4747884">[2] Preuer, Kristina, et al. "DeepSynergy: predicting anti-cancer drug synergy with Deep Learning." Bioinformatics 34.9 (2018): 1538-1546.
</a> 

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr />


### DrugComb

<p class='is-size-6'>  <strong> Dataset Description: </strong> This dataset contains the summarized results of drug combination screening studies for the NCI-60 cancer cell lines (excluding the MDA-N cell line). A total of 129 drugs are tested across 59 cell lines resulting in a total of 297098 unique drug combination-cell line pairs. For each of the combination drugs, we provide its canonical SMILES string queried from PubChem. For each cell line, we include the following features downloaded from NCI’s CellMiner interface: 25,723 gene features capturing transcript expression levels averaged from five microarray platforms, 627 microRNA expression features and 3171 proteomic features that capture the abundance levels of a subset of proteins. </p>

<p class='is-size-6'> There are two kinds of labels included in this dataset. CSS measures the drug combination sensitivity and is derived using relative IC50 values of compounds and the area under their dose-response curves. The other four metrics capture the synergy between the two drugs. Synergy is a dimensionless measure of deviation of an observed drug combination response from the expected effect of non-interaction. Synergy is calculated using four different models: Bliss model, Highest Single Agent (HSA), Loewe additivity model and Zero Interaction Potency (ZIP).
</p>

<p class='is-size-6'>  <strong> Task Description: </strong>Given the chemical structural information for the combining drugs and genomic features for a particular cell line, predict the drug synergy level or the drug combination sensitivity in that cell line.</p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 129 drugs are tested across 59 cell lines resulting in a total of 297098 unique drug combination-cell line pairs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> <span class="tag is-info is-light">Cold Cell Line Split</span> </p>

``` python
from tdc.multi_pred import DrugSyn
data = DrugSyn(name = 'DrugComb')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://academic.oup.com/nar/article-abstract/47/W1/W43/5486743">[1] Zagidullin, Bulat, et al. “DrugComb: an integrative cancer drug combination data portal.” Nucleic acids research 47.W1 (2019): W43-W51. </a> 

<a href="https://mayoclinic.pure.elsevier.com/en/publications/cellminer-a-web-based-suite-of-genomic-and-pharmacologic-tools-to">[2] Reinhold, William C., et al. "CellMiner: a web-based suite of genomic and pharmacologic tools to explore transcript and drug patterns in the NCI-60 cell line set." Cancer research 72.14 (2012): 3499-3511.
</a> 

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr />