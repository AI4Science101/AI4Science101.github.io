---
title: News
subtitle:
layout: page
show_sidebar: false
hide_hero: true
---

# News
<hr />
<p class="is-size-5"><strong>2022.11.03</strong> TDC <code>0.3.8</code> is released! Here are the changes: </p>

<ul class="is-medium">
    <li> TDC has a new task on structure-based drug design <code>SBDD</code> with four datasets PDBBind, DUD-E, scPDB. See <a href="/generation_tasks/sbdd/"> here </a> on how to access them!</li>
    <li> To support evaluation of SBDD tasks, we also include two evaluation metrics (RMSD, Kabsch-RMSD) that compare distances between two structures. See <a href="/functions/data_evaluation/#rmsd">here</a> for more info.</li>    
    <li> TDC has a new dataset on  PAMPA (parallel artificial membrane permeability assay), which is a commonly employed assay to evaluate drug permeability across the cellular membrane in the <code>ADME</code> task. See <a href="/single_pred_tasks/adme/#pampa-permeability-ncats"> here </a> for more info!</li>
</ul>


<hr />
<p class="is-size-5"><strong>2022.09.06</strong> TDC <code>0.3.7</code> is released! Here are the changes: </p>

<ul class="is-medium">
    <li> TDC has a new evaluation metric on logAUC. See <a href="/functions/data_evaluation/#range-logauc"> here </a> and the <a href="https://github.com/mims-harvard/TDC/pull/152">PR</a>.</li>
    <li> TDC now supports graphein protein 3D representation for antibody develop-ability prediction. See <a href="https://github.com/mims-harvard/TDC/blob/main/tutorials/graphein_demo_developability.ipynb">tutorial</a> and the <a href="https://github.com/mims-harvard/TDC/pull/159">PR</a>.</li>
    <li> <code>QM</code> task are now in 3D format. See <a href="https://github.com/mims-harvard/TDC/pull/160">here</a>.</li>
    <li> TDC has a harmonize function to deal with duplicated experimental entries in DTI. See <a href="https://github.com/mims-harvard/TDC/pull/162">here</a>.</li>
    <li> TDC now has a dataloader for PrimeKG as an auxilliary resource. See how to access PrimeKG <a href="/resources/overview/#precision-medicine-knowledge-graph-primekg">here</a>.</li>
    <li> TDC fixed static scikit-learn version issue for gsk3b, jnk3, drd2 oracles. See <a href="https://github.com/mims-harvard/TDC/pull/168">here</a> for more info.</li>
    <li> The PPBR dataset in ADME task now has additional species information and the default is now only containing homo sapiens while you can retrieve other species via a TDC function. See <a href="/single_pred_tasks/adme/#ppbr-plasma-protein-binding-rate-astrazeneca">here</a> for more info.</li>
    
</ul>

<hr />

<p class="is-size-5"><strong>2022.02.19</strong> TDC <code>0.3.6</code> is released! TDC has a new task on TCR-Epitope Binding prediction  (Thanks to Anna and Jannis)! Checkout <a href="/multi_pred_tasks/tcrepitope/">here</a> for more information.</p>

<hr />
<p class="is-size-5"><strong>2022.01.23</strong> TDC <code>0.3.5</code> is released! Here are the changes: </p>

<ul class="is-medium">
    <li> TDC has a new large hERG dataset in <code>Tox</code> (Thanks to <a href="https://github.com/benb111">Ben</a>)! Checkout <a href="/single_pred_tasks/tox/#herg-central">here</a> for more information.</li>
</ul>

<ul class="is-medium">
    <li> TDC has an updated ChEMBL library (Version 29) in <code>MolGen</code>! The previous version is also still kept available. Checkout <a href="/generation_tasks/molgen/#chembl">here</a> for more information.</li>
</ul>

<ul class="is-medium">
    <li> Reaction type information can be found within split by turning on the include_reaction_type flag for USPTO-50 in <code>RetroSyn</code>!  Checkout <a href="/generation_tasks/retrosyn/#uspto-50k">here</a> for more information.</li>
</ul>

<ul class="is-medium">
    <li> Fixed bug on cold split for higher order (>2) multi-instance prediction tasks! (Thanks to <a href="https://github.com/ZOE-V">Zoe</a> !)  Checkout <a href="https://github.com/mims-harvard/TDC/issues/136">here</a> for more information.</li>
</ul>

<hr />
<p class="is-size-5"><strong>2021.12.28</strong> TDC <code>0.3.4</code> is released! Bug fixes on docking oracles and KL divergence measure. </p>

<hr />

<hr />
<p class="is-size-5"><strong>2021.11.25</strong> TDC <code>0.3.3</code> is released! Now added extended support for cold split in multi prediction tasks, see <a href="https://github.com/mims-harvard/TDC/pull/127">this issue</a>! </p>

<hr />
<p class="is-size-5"><strong>2021.10.17</strong> TDC <code>0.3.2</code> is released! We have added support for harmonizing same DTIs with different affinities (KIBA, DAVIS Updated accordingly, see <a href="https://github.com/mims-harvard/TDC/issues/98">this issue</a>); support for label name retrieval for TWOSIDES (<a href="https://github.com/mims-harvard/TDC/issues/121">this issue</a>), and add gene symbol info to GDSC (<a href="https://github.com/mims-harvard/TDC/issues/122">this issue</a>).</p>

<hr />
<p class="is-size-5"><strong>2021.09.04</strong> TDC <code>0.3.0</code> is released! We have greatly restructured the code to be contributor friendly while keeping most interfaces the same. We also release the documentation for TDC package at <a href="https://tdc.readthedocs.io/">here</a>.</p>
<hr />

<p class="is-size-5"><strong>2021.05.30</strong> TDC updates to <code>0.2.0</code>, major changes:</p>

<ul class="is-medium">
    <li> TDC has a new molecule generation benchmark on docking scores! Checkout <a href="/benchmark/docking_group/overview">here</a> for more information.</li>
</ul>

<hr />

<p class="is-size-5"><strong>2021.03.24</strong> TDC updates to <code>0.1.9</code>, major changes:</p>

<ul class="is-medium">
    <li> TDC now supports molecule filters! Checkout <a href="/functions/data_process/#molecule-filters">here</a> for more information.</li>
</ul>

<hr />

<p class="is-size-5"><strong>2021.03.17</strong> TDC updates to <code>0.1.8</code>, major changes:</p>

<ul class="is-medium">
    <li> Leaderboard is reformulated and we invite submission for each individual benchmark! Checkout <a href="/benchmark/overview">here</a> for more information.</li>
</ul>

<hr />

<p class="is-size-5"><strong>2021.02.26</strong> TDC updates to <code>0.1.7</code>, major changes:</p>

<ul class="is-medium">
    <li> Streamlined leaderboard programming framework! Checkout <a href="/benchmark/overview">here</a> for more information.</li>
    <li> Label log transformation supported. Checkout <a href="/functions/data_process/#label-units-conversion">here</a> for more information.</li>
</ul>

<hr />

<p class="is-size-5"><strong>2021.02.18</strong> TDC just released the white paper in arXiv! Here is the <a href="https://arxiv.org/abs/2102.09548">link</a> to the paper.

<hr />

<p class="is-size-5"><strong>2021.02.04</strong> TDC updates to <code>0.1.6</code>, major changes:</p>

<ul class="is-medium">
    <li><strong> New Leaderboard! </strong> Just released the second leaderboard on drug combination response prediction! Checkout <a href="/benchmark/drugcombo_group">here</a> for usage.</li>
</ul>

<hr />

<p class="is-size-5"><strong>2021.01.16</strong> TDC updates to <code>0.1.5</code>, major changes:</p>

<ul class="is-medium">
    <li><strong> New Oracles! </strong> Added four realistic oracles from docking scores and synthetic accessibility scores! Checkout <a href="/functions/oracles">here</a> for usage.</li>
</ul>

<hr />

<p class="is-size-5"><strong>2021.01.09</strong> TDC updates to <code>0.1.4</code>, major changes:</p>

<ul class="is-medium">
    <li><strong> New Function! </strong> Added a data processing helper to map among ~15 molecular formats in 2 lines of code (For 2D: from SMILES/SEFLIES and convert to SELFIES/SMILES, Graph2D, PyG, DGL, ECFP2-6, MACCS, Daylight, RDKit2D, Morgan, PubChem; For 3D: from XYZ, SDF files to Graph3D, Columb Matrix). Checkout <a href="/functions/data_process/#molecule-conversion">here</a> for usage.</li>
    <li><strong> Quality Check! </strong> Canonicalize SMILES on DTI datasets with Drug, Target IDs added. Checkout <a href="/multi_pred_tasks/DTI/"><code>DTI</code></a>.</li>
</ul>

<hr />

<p class="is-size-5"><strong>2020.12.30</strong> TDC updates to <code>0.1.3</code>, major changes:</p>

<ul class="is-medium">
    <li><strong> New Dataset! </strong> Added a new therapeutic task CRISPR Repair Outcome Prediction! Checkout <a href="/single_pred_tasks/CRISPROutcome/"><code>CRISPROutcome</code></a>.</li>
    <li><strong> New Function! </strong> Added a data processing helper to map SMILES string to popular cheminformatics fingerprints (ECFP2, ECFP4, ECFP6, MACCS, Daylight-type, RDKit2D, Morgan, Pubchem)! Checkout <a href="/functions/data_process/#molecular-fingerprint-mapping">here</a> for usage.</li>
</ul>

<hr />

<p class="is-size-5"><strong>2020.12.24</strong> TDC updates to <code>0.1.2</code>, major changes:</p>

<ul class="is-medium">
    <li><strong> Leaderboard Release! </strong> TDC's first leaderboard on ADMET prediction is released. You can find the leaderboard guide <a href="/benchmark/overview">here</a>, where we provide a <code>BenchmarkGroup</code> class to do model building on leaderboard tasks rapidly. The ADMET leaderboard is <a href="/benchmark/admet_group/">here</a>.</li>
</ul>

<hr />

<p class="is-size-5"><strong>2020.12.19</strong> TDC updates to <code>0.1.1</code>, major changes:</p>

<ul class="is-medium">
    <li><strong> Quality Check and New datasets! </strong> We replaced VD, Half Life and Clearance datasets in <code>ADME</code> from new sources that have higher qualities. We also added LD50 to <code>Tox</code>.  </li>
</ul>

<hr />

<p class="is-size-5"><strong>2020.12.15</strong> TDC updates to <code>0.1.0</code>, major changes:</p>

<ul class="is-medium">
    <li><strong> Five New Datasets! </strong> Added CYP2C9/2D6/3A4 Substrate, for <code>ADME</code>, Carcinogens for <code>Tox</code> and NCI-60 for <code>DrugSyn</code>. </li>
    <li><strong>Quality Check.</strong> We conducted a canonicalization of all SMILES and removed ones that return errors in the <code>ADME</code>, <code>Tox</code>, and <code>HTS</code> datasets. </li>
</ul>

<hr />

<p class="is-size-5"><strong>2020.11.30</strong> TDC updates to <code>0.0.8</code>, major changes:</p>

<ul class="is-medium">
    <li><strong> Five New Datasets! </strong> Added hREG, DILI (Drug Induced Liver Injury), Skin Reaction, Ames Mutagenicity for <code>Tox</code> and PPBR from AstraZeneca for <code>ADME</code>. </li>
    <li><strong>Distribution Learning Metrics Moved to Evaluators.</strong> Checkout <a href="{{ "/functions/data_evaluation" | relative_url }}"> here </a> for the updated usage.</li>
    <li><strong>Meta Oracles.</strong> We included a helper function where you can specify your own set of molecules for Rediscovery, Similarity, Medians, Isomers. Checkout an example usage <a href="{{ "functions/oracles/#rediscovery" | relative_url }}"> here</a>. </li>
    <li><strong>Tutorials.</strong> We have provided various tutorials for you to start using TDC. Click <a href="https://github.com/mims-harvard/TDC/tree/master/tutorials"> here </a>.
 </li>
</ul>

<hr />
