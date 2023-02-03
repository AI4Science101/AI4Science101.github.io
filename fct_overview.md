---
title: TDC Data Functions
subtitle: 
layout: page
show_sidebar: false
hide_hero: true
---

# Overview of TDC Data Functions

<div class="container">
        <div class="columns is-vcentered">
            <div class="column is-7">
                <p class="is-size-5">TDC implements a comprehensive suite of functions frequently used in therapeutics ML. This functionality is available through an easy-to-use interface.</p>
                <p class="is-size-5">Broadly, TDC functions cover the following four major categories:</p>
                <ul class="is-size-5">
                    <li><strong>Model Evaluation</strong>: TDC implements a series of metrics and performance functions to debug ML models, evaluate model performance for any task in TDC, and assess whether model predictions generalize to out-of-distribution datasets. </li>
                    <li><strong>Dataset Splits</strong>: Therapeutic applications require ML models to generalize to out-of-distribution samples. TDC implements various data splits to reflect real-world settings.</li>
                    <li><strong>Data Processing</strong>: As therapeutic ML covers a wide range of data modalities and requires numerous repetitive processing functions, TDC implements wrappers and useful data helpers. </li>
                    <li><strong>Molecule Generation Oracles</strong>: Molecular design tasks require oracle functions to measure the quality of generated entities. TDC provides molecule generation oracles, representing the most comprehensive collection of molecule oracles. Every oracle is tailored to measure the quality of AI-generated molecules in a specific dimension. </li>
                </ul>
            </div>
            <div class="column is-5 has-text-centered">
                <img src="{{ "/img/tdc_fct_overview.png" | relative_url }}" alt="TDC logo" class="img-responsive">
            </div>
        </div>
</div>

<div class="column is-12">
    <hr />
</div>

<p class="is-size-3 has-text-centered"> <strong> Start Exploring TDC Functions </strong> </p>

<div class="container">
        <div class="columns is-vcentered is-size-5">
            <div class="column is-3 has-text-centered"> <a href="/functions/data_evaluation" class="box has-background-info has-text-white">Model Evaluation</a></div>
            <div class="column is-3 has-text-centered"> <a href="/functions/data_process" class="box has-background-info has-text-white">Data Processing</a></div>
            <div class="column is-3 has-text-centered"> <a href="/functions/data_split" class="box has-background-info has-text-white">Data Split</a></div>
            <div class="column is-3 has-text-centered"> <a href="/functions/oracles" class="box has-background-info has-text-white">Molecule Oracles</a></div>
        </div>
</div>
