---
title: Quick Start
subtitle:
layout: page
show_sidebar: false
hide_hero: true
---

# Introduction

<p class="is-size-5"> 
Developing therapeutics to cure diseases and improve human health is an overarching goal of biomedical research. The Commons supports the development of artificial intelligence (AI) and machine learning (ML) methods, with a strong bent towards developing the foundations of which ML methods are most suitable for drug discovery applications and why.
</p>

<p class="is-size-5">
The Commons provides access to ML capability across therapeutic modalities and stages of discovery. It contains solvable ML tasks, ML-ready datasets, and curated benchmarks and leadearboards, all accessible via a Python package. Datasets in the Commons cover a wide range of therapeutic products (e.g., small molecules, biologics, gene editing therapies) across the entire discovery and development pipeline (e.g., target identification, hit discovery, lead optimization, manufacturing). 
</p>

<div class="column is-8 is-offset-2">
    <img src="{{ "/img/tdc_triangle.png" | relative_url }}" alt="Overview of TDC" class="img-responsive">
</div>

<p class="is-size-5">
All datasets are ML-ready, meaning that input features are processed into an accessible format, such that scientists can use them directly as input to ML methods. TDC provides numerous functions for model evaluation, meaningful data splits, data processors, and oracles for molecule generation. All features of TDC are designed to easily integrate into any ML project, supporting the entire lifecycle of the project. 
</p>

<p class="is-size-5">
The Commons curates benchmarks for key therapeutic tasks. Every benchmark has a carefully designed ML task, ML-ready dataset, a public leaderboard, and a set of performance metrics to support model evaluation, providing effective indicators of the performance of ML methods in real-world scenarios.
</p>

<div class="container">
            <div class="columns is-vcentered">
                <div class="column is-12 is-size-5">
                    <div class="box has-background-info has-text-white">
                        <b>Enable algorithmic and scientific advance in therapeutic science</b><br/>
                        The Commons lies at the nexus between artificial intelligence and drug discovery. Biologists and biochemists can
                        pose ML tasks and identify relevant datasets that are carefully processed and integrated into Commons and formulated as scientifically valid ML tasks. ML scientists can rapidly obtain these tasks and develop ML methods to advance the therapeutic task past the state of the art and open up new opportunities.
                    </div>
                </div>
            </div>
</div>

<img src="{{ "/img/tdc_vision.png" | relative_url }}" alt="Vision for TDC" class="img-responsive">

<div class="column is-12">
    <hr />
</div>

## Tiered Design of Therapeutics Data Commons: "Problem -- ML Task -- Dataset" 

<div class="container">
    <div class="columns is-vcentered">
        <div class="column is-8">
              <p class="is-size-5">
              TDC has an unique three-tiered hierarchical structure. At the highest level, its resources are organized to support three types of <b>problems</b>. For each problem, we give a collection <b>ML tasks</b>. Finally, for each task, we provide a series of <b>datasets</b>.
              </p> 
              <p class="is-size-5">
              The Commons outlines three major problems in the first tier:
              </p>
              <ul>
                <li><strong>Single-instance prediction </strong> <code>single_pred</code>: Making predictions involving individual biomedical entities. </li>
                <li><strong>Multi-instance prediction </strong><code>multi_pred</code>: Making predictions about multiple biomedical entities. </li>
                <li><strong>Generation</strong> <code>generation</code>: Generating new biomedical entities with desirable properties. </li>
              </ul>
        </div>
        <div class="column is-3 has-text-centered">
            <img src="{{ "/img/tdc_hierarchy.png" | relative_url }}" alt="TDC hierarchy" class="img-responsive">
        </div>
    </div>
</div>

<div class="container">
    <div class="columns is-vcentered">
        <div class="column is-8">
              <p class="is-size-5">
              At the second tier, TDC is organized into ML tasks. Researchers across disciplines can use ML tasks for numerous applications, including identifying personalized combinatorial therapies, designing novel class of antibodies, improving disease diagnosis, and finding new cures for emerging diseases.
        </p>
        <p class="is-size-5">
        In the third tier, we provide multiple datasets for each task. For each dataset, we provide several splits of the dataset into training, validation, and test sets to evaluate model performance.
        </p>
              <p class="is-size-5"> </p>
        </div>
        <div class="column is-3 has-text-centered">
            <img src="{{ "/img/tdc_problems.png" | relative_url }}" alt="TDC problems" class="img-responsive">
        </div>
    </div>
</div>


<div class="column is-12">
    <hr />
</div>

## Installation

<p class="is-size-5"> To install the TDC Python package, use the following: </p>

```bash
pip install PyTDC
```

<p class="is-size-5"> The installation of the package is hassle-free with minimum dependency on external packages. </p>

<div class="column is-12">
    <hr />
</div>


## Data Loaders

<p class="is-size-5">  TDC provides intuitive, high-level APIs for both beginners and experts to create ML models in Python. Building off the modularized "Problem--ML Task--Dataset" structure, TDC provides a three-layer API to access any ML task and dataset.  
</p> 


<div class="column is-8 is-offset-2">
    <img src="{{ "/img/tdc_API_relation2.png" | relative_url }}" alt="TDC api" class="img-responsive">
</div>

<p class="is-size-5"> As an example, to obtain the <code>Caco2</code> dataset from <code>ADME</code> task in the <code>single-instance prediction</code> problem do as follows: </p>

```python
from tdc.single_pred import ADME
data = ADME(name = 'Caco2_Wang')
df = data.get_data()
splits = data.get_split()
```
<p class="is-size-5"> The variable <code>df</code> is a Pandas object holding the entire dataset. By default, the variable <code>splits</code> is a dictionary with keys <code>train</code>, <code>val</code>, and <code>test</code> whose values are all Pandas DataFrames with Drug IDs, SMILES strings and labels. For detailed information about outputs, see <a href="/single_pred_tasks/adme/#caco-2-cell-effective-permeability-wang-et-al">Datasets documentation.</a> </p>

<p class="is-size-5"> The user only needs to specify "Problem -- ML Task -- Dataset." TDC then automatically retrieves the processed ML-ready dataset from the TDC server and generates a <code>data</code> object, exposing numerous data functions that can be directly applied to the dataset. </p>

<div class="column is-12">
    <hr />
</div>

## Ecosystem of Data Functions, Tools, Libraries, and Community Resources

<p class="is-size-5"> TDC includes numerous data functions to support the development of novel ML methods and theory: </p>
<ul class="is-size-5">
    <li><strong>Model Evaluation</strong>: TDC implements a series of metrics and performance functions to debug ML models, evaluate model performance for any task in TDC, and assess whether model predictions generalize to out-of-distribution datasets.</li>
    <li><strong>Dataset Splits</strong>: Therapeutic applications require ML models to generalize to out-of-distribution samples. TDC
implements various data splits to reflect realistic learning settings. </li>
    <li><strong>Data Processing</strong>: As therapeutics ML covers a wide range of data modalities and requires numerous repetitive
processing functions, TDC implements wrappers and useful data helpers for them. </li>
    <li><strong>Molecule Generation Oracles</strong>: Molecular design tasks require oracle functions to measure the quality of generated entities. TDC implements over 17 molecule generation oracles, representing the most comprehensive colleciton of molecule oracles. Each oracle is tailored to measure the quality of AI-generated molecules in a specific dimension.</li>
  </ul>

<div class="column is-12">
    <hr />
</div>

## Public Leaderboards and Benchmarks

<p class="is-size-5">
TDC provides leaderboards for systematic model evaluation and comparison. Every dataset
in TDC can be thought of as a <b>benchmark</b>. For a model to be useful for a specific therapeutic question,
it needs to consistently perform well across multiple datasets and tasks. For this reason, we group
individual benchmarks into meaningful groups centered around therapeutic questions, which we refer to as <b>benchmark groups</b>. Dataset splits and evaluation metrics reflect real-world difficulty of therapeutic problems.
</p>

<div class="column is-12">
    <hr />
</div>

<!--
## Cite Therapeutics Data Commons

<p class="is-size-5"> If you use TDC in your work, consider citing our <b><a href="https://openreview.net/pdf?id=8nvgnORnoWr">NeurIPS 2021 Datasets and Benchmarks paper:</a></b> </p>

```
@article{Huang2021tdc,
  title={Therapeutics Data Commons: Machine Learning Datasets and Tasks for Drug Discovery and Development},
  author={Huang, Kexin and Fu, Tianfan and Gao, Wenhao and Zhao, Yue and Roohani, Yusuf and Leskovec, Jure and Coley, 
          Connor W and Xiao, Cao and Sun, Jimeng and Zitnik, Marinka},
  journal={Proceedings of Neural Information Processing Systems, NeurIPS Datasets and Benchmarks},
  year={2021}
}
```

<p class="is-size-5"> If you use any of the datasets, make sure to also cite the primary data source as described in <a href="overview/">Datasets section.</a> </p>

<div class="column is-12">
    <hr />
</div>
-->

<p class="is-size-3 has-text-centered"> <strong>Explore Therapeutics Data Commons</strong> </p>

<div class="container">
        <div class="columns is-vcentered is-size-5">
            <div class="column is-4 has-text-centered"> <a href="/overview" class="box has-background-info has-text-white">Overview of Datasets</a></div>
            <div class="column is-4 has-text-centered"> <a href="/fct_overview" class="box has-background-info has-text-white">Overview of Data Functions</a></div>
            <div class="column is-4 has-text-centered"> <a href="/benchmark/overview" class="box has-background-info has-text-white">Overview of Benchmarks</a></div>
        </div>
</div>