---
title: Resources
subtitle: 
toc: true
layout: page
show_sidebar: false
menubar: resources
hide_hero: true
---

### Workshop

<p class='is-size-6'>  <strong> Description: </strong>  Developing personalized diagnostic strategies and targeted treatments requires a deep understanding of disease biology and the ability to dissect the relationship between molecular and genetic factors and their phenotypic consequences. However, such knowledge is fragmented across publications, non-standardized research repositories, and evolving ontologies describing various scales of biological organization between genotypes and clinical phenotypes. </p>


<p class='is-size-6'> PrimeKG is a precision medicine-oriented knowledge graph that provides a holistic view of diseases. PrimeKG integrates 20 high-quality resources to describe 17,080 diseases with 4,050,249 relationships representing ten major biological scales, including disease-associated protein perturbations, biological processes and pathways, anatomical and phenotypic scales, and the entire range of approved and experimental drugs with their therapeutic action, considerably expanding previous efforts in disease-rooted knowledge graphs. </p>

<p class='is-size-6'>PrimeKG supports drug-disease prediction by including an abundance of `indications’, `contradictions’ and `off-label use’ edges, which are usually missing in other knowledge graphs. In addition to the graph structure, PrimeKG includes text descriptions of clinical guidelines for drugs and diseases to enable multimodal analyses.</p>

``` python
from tdc.resource import PrimeKG
data = PrimeKG(path = './data')
drug_feature = data.get_features(feature_type = 'drug')
data.to_nx()
data.get_node_list(type = 'disease')
```

<p class='is-size-6'>  <strong> Click <a href="https://zitniklab.hms.harvard.edu/projects/PrimeKG/">here</a> to learn more.</strong> </p>


<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://www.biorxiv.org/content/10.1101/2022.05.01.489928">[1] Chandak, Payal, Kexin Huang, and Marinka Zitnik. “Building a knowledge graph to enable precision medicine.” bioRxiv (2022).
</a> 


### Biomedical Knowledge Graph HetioNet

<p class='is-size-6'>  <strong> Description: </strong> Hetionet is an integrative network encoding knowledge from millions of biomedical studies. Data were integrated from 29 public resources to connect compounds, diseases, genes, anatomies, pathways, biological processes, molecular functions, cellular components, pharmacologic classes, side effects, and symptoms. </p>

<p class='is-size-6'>  <strong> Click <a href="https://het.io/">here</a> to visit.</strong> </p>


<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://elifesciences.org/articles/26726">[1] Himmelstein, Daniel Scott, et al. "Systematic integration of biomedical knowledge prioritizes drugs for repurposing." Elife 6 (2017): e26726.
</a> 

<a href="https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1004259"> [2] Himmelstein, Daniel S., and Sergio E. Baranzini. "Heterogeneous network edge prediction: a data integration approach to prioritize disease-associated genes." PLoS Comput Biol 11.7 (2015): e1004259.
</a>


### Drug Repurposing Library

<p class='is-size-6'>  <strong> Description: </strong> The Drug Repurposing Hub is a curated and annotated collection of FDA-approved drugs, clinical trial drugs, and pre-clinical tool compounds with a companion information resource. Order library plates to screen yourself or collaborate with the Broad Institute’s Center for the Development of Therapeutics to see if an existing drug may work against your novel target, model system, or indication. While the collection will undoubtedly reveal new uses for developed drugs, its true power is unlocked when applied to discover new biological insights and disease mechanisms. </p>

<p class='is-size-6'>  <strong> Click <a href="https://clue.io/repurposing">here</a> to visit.</strong> </p>


<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://www.nature.com/articles/nm.4306?">[1] Corsello, Steven M., et al. "The Drug Repurposing Hub: a next-generation drug library and information resource." Nature medicine 23.4 (2017): 405-408.
</a> 
