---
layout: home
permalink: /tutorials/
title: Seldonian \| Tutorials
---

<div class="container mt-4" align="center">
    <a href="{{ "/overview/" | relative_url }}" class="btn btn-primary">&laquo; Previous: Overview</a>
    <a href="{{ "/tutorials/alg_details_tutorial/" | relative_url }}" class="btn btn-primary">Next: (A) Seldonian algorithm details &raquo;</a>
</div>

<!-- Main Container -->
<div class="container p-3 my-4 border" style="background-color: #f3f4fc;">
    <h5 class="mb-3"><b>Getting started</b></h5>
    <hr class="my-4">
    <p>Whether you are interested in Seldonian algorithms for supervised learning or reinforcement learning, this is the place to start. We have created a list of seven tutorials, labeled A–G, which may be helpful before running your own Seldonian algorithms. We recommend starting with "The Basics," tutorials A–C, regardless of which track you choose. Reinforcement learning is a more advanced topic than supervised learning, which is why we recommend one of the supervised learning tutorials for that track as well.</p>

    <div class="container inset-box border border-dark border-2 p-3 my-2">
        <h5>The Basics (start here)</h5>

        <ol>
            <li>
                <a href="{{ "/tutorials/alg_details_tutorial/" | relative_url}}">(A) Seldonian algorithm details</a>
            </li>
            <li>
                <a href="{{ "/tutorials/install_toolkit_tutorial/" | relative_url}}">(B) Installing the Seldonian Toolkit</a>
            </li>
            <li>
                <a href="{{ "/tutorials/simple_engine_tutorial/" | relative_url}}">(C) Running the Seldonian Engine</a>
            </li>
        </ol>
    </div>

    <div class="container inset-box border border-dark border-2 p-3 my-2">
        <h5>Supervised learning track </h5>

        <ol>
            <li>
                <a href="{{ "/tutorials/fair_loans_tutorial/" | relative_url}}">(D) Fairness for automated loan approval systems</a>
            </li>
            <li>
                <a href="{{ "/tutorials/science_GPA_tutorial/" | relative_url}}">(E) Predicting student GPAs from application materials with fairness guarantees</a>
            </li>

            <li>
                <a href="{{ "/tutorials/pytorch_mnist/" | relative_url}}">(F) Creating a new Seldonian supervised learning model </a>
            </li> 

            <li>
                <a href="{{ "/tutorials/pytorch_mnist/" | relative_url}}">(G) Creating your first Seldonian PyTorch model</a>
            </li> 

            <li>
                <a href="{{ "/tutorials/dtree_tutorial/" | relative_url}}">(L) Creating Fair Decision Trees and Random Forests (for binary classification)</a>
            </li> 

            <li>
                <a href="{{ "/tutorials/parallelization_tutorial/" | relative_url}}"> (M) Efficient parallelization with the toolkit </a>
            </li>

            <li>
                <a href="{{ "/tutorials/addl_datasets_tutorial/" | relative_url}}"> (N) Using multiple datasets with the toolkit </a>
            </li>

        </ol>
    </div>

    <div class="container inset-box border border-dark border-2 p-3 my-2">
        <h5>Reinforcement learning track </h5>

        <ol>
            <li>
                <a href="{{ "/tutorials/fair_loans_tutorial/" | relative_url}}">(D) Fairness for automated loan approval systems</a>
            </li>
            <li>
                <a href="{{ "/tutorials/gridworld_RL_tutorial/" | relative_url}}">(H) Introduction to reinforcement learning with the Seldonian Toolkit</a>
            </li>

            <li>
                <a href="{{ "/tutorials/parallelization_tutorial/" | relative_url}}"> (M) Efficient parallelization with the toolkit </a>
            </li>
        </ol>
    </div>

    <div class="container inset-box border border-dark border-2 p-3 my-2">
        <h5>Advanced (for developers) </h5>
        <ol>
            <li>
                <a href="{{ "/tutorials/custom_base_variable_tutorial/" | relative_url}}"> (I) Creating custom base variables in behavioral constraints</a>
            </li>
            <li> <a href="{{ "/tutorials/efficient_deep_networks/" | relative_url}}"> (J) Efficiently training deep Seldonian networks</a></li>

            <li> <a href="{{ "/tutorials/new_baseline/" | relative_url}}"> (K) Creating a new baseline for (supervised) Seldonian Experiments</a></li>


        
        </ol>

    </div>
</div>