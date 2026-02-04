# 🎓 Master’s Level Causal Inference: The Unified Syllabus

## 🟦 PHASE 1: The Foundations of Causal Reasoning
*Bridging the gap between "what happened" (prediction) and "why it happened" (intervention).*

### Module 0: Causal Thinking Before Models (Grounding)
* **Theory:** Correlation vs. Causation; Observational vs. Interventional data.
* **Core Idea:** Why high predictive accuracy does not imply correct decision-making.
* **Pathao Case:** Why a perfectly accurate churn model might suggest "useless" discounts if it doesn't account for user price-sensitivity.
* **CGM Case:** Why seeing "high glucose" and "high insulin" simultaneously doesn't mean insulin causes high glucose (The Association Trap).

* **Topic-wise Reading List (with links):**
    * **Correlation ≠ causation (intuition + classic failure modes):** entity["book","Causal Inference: The Mixtape","online edition"] — Chapter 1 (“Do Not Confuse Correlation with Causality” and decision-driven examples). `https://mixtape.scunning.com/01-introduction`. citeturn21view0
    * **Prediction vs intervention (data science framing):** “Prediction vs causal inference” (British Psychological Society). `https://www.bps.org.uk/psychologist/prediction-vs-causal-inference`. citeturn0search15
    * **Description vs prediction vs causal inference (research taxonomy used in applied DS):** “Distinguishing Description, Prediction, and Causal Inference” (Neurology, 2025). `https://www.neurology.org/doi/10.1212/WNL.0000000000210171`. citeturn0search11
    * **The “ladder” mindset (association → intervention → counterfactuals):** entity["book","The Book of Why: The New Science of Cause and Effect","basic books 2018"] — publisher page and synopsis. `https://www.basicbooks.com/titles/judea-pearl/the-book-of-why/9780465097616/`. citeturn22search0
    * **Counterfactual-first “what would happen if…” fundamentals:** entity["book","Causal Inference: What If","hernan robins online"] — free online book PDF (regularly updated). `https://content.sph.harvard.edu/wwwhsph/sites/1268/2024/01/hernanrobins_WhatIf_2jan24.pdf`. citeturn0search0
    * **Decision-making lens (formal “actions cause outcomes” framing):** Stanford Encyclopedia of Philosophy, “Causal Decision Theory” (updated 2024). `https://plato.stanford.edu/entries/decision-causal/`. citeturn0search7

### Module 1: The Potential Outcomes Framework (Rubin Model)
* **Theory:** Counterfactuals $Y_i(1), Y_i(0)$; The Fundamental Problem of Causal Inference.
* **Mathematics:** * Average Treatment Effect: $ATE = E[Y(1) - Y(0)]$
    * Selection Bias Decomposition: $E[Y|T=1] - E[Y|T=0] = ATE + \{E[Y(0)|T=1] - E[Y(0)|T=0]\}$
* **Assumptions:** SUTVA, Ignorability, and Positivity (Overlap).
* **Python Strategy:** Simulating counterfactual data distributions using `CausalML`.

* **Topic-wise Reading List (with links):**
    * **Potential outcomes & the “fundamental problem” (core explanation + examples):** entity["book","Causal Inference: What If","hernan robins online"] — official book page (use Part I). `https://miguelhernan.org/whatifbook`. citeturn0search4
    * **Rubin model walk-through (MS-friendly, structured notes):** Stanford POLISCI handout “Potential Outcomes and Causal Inference I.” `https://web.stanford.edu/class/polisci350c/classonly/causal.pdf`. citeturn13search2
    * **ATE / identification / practical learning path:** entity["book","Causal Inference: The Mixtape","online edition"] — Chapter 4 “Potential Outcomes Causal Model.” `https://mixtape.scunning.com/04-potential_outcomes`. citeturn20view1
    * **SUTVA + assignment mechanisms (clear lecture-style grounding):** “Introduction to Potential Outcomes” handout. `https://sites.stat.washington.edu/tsr/simons/simons-lecture1-handout.pdf`. citeturn13search13
    * **Reference textbook for formality (estimands, assignment, inference):** entity["book","Causal Inference for Statistics, Social, and Biomedical Sciences","cambridge 2015"] — Cambridge University Press book page. `https://www.cambridge.org/core/books/causal-inference-for-statistics-social-and-biomedical-sciences/71126BE90C58F1A431FE9B2DD07938AB`. citeturn13search0
    * **Python (counterfactual simulation + treatment/value framing in `CausalML`):** CausalML quickstart + counterfactual value estimator notebook. `https://causalml.readthedocs.io/en/latest/quickstart.html` and `https://causalml.readthedocs.io/en/latest/examples/counterfactual_value_optimization.html`. citeturn13search14turn13search3

### Module 2: Structural Causal Models & DAGs (Pearlian School)
* **Theory:** The Logic of Intervention ($do$-calculus intuition).
* **Mathematics:** * **The Backdoor Criterion:** $P(y|do(x)) = \sum_z P(y|x,z)P(z)$
    * **Graphical Anatomy:** Confounders, Mediators, and the "Data Scientist's Nightmare": The Collider.
* **CGM Application:** Mapping the system: $Diet \rightarrow Glucose \leftarrow Insulin$. Identifying collider bias in blood sugar explanations.
* **Python Strategy:** Building and visualizing DAGs with `NetworkX` and `DoWhy`.

* **Topic-wise Reading List (with links):**
    * **SCMs, DAGs, identifying effects, backdoor/colliders (best “primer” to master):** entity["book","Causal Inference in Statistics: A Primer","wiley 2016"] — complete PDF (commonly used as a first DAG text). `https://web.cs.ucla.edu/~kaoru/primer-complete-2019.pdf`. citeturn8search1
    * **Do-operator intuition + graphical identification viewpoint (survey-level):** “Causal inference in statistics: An overview” (Statistics Surveys). `https://ftp.cs.ucla.edu/pub/stat_ser/r350.pdf`. citeturn8search17
    * **DAG notation, backdoor, collider bias (applied and readable):** Mixtape Chapter 3 “Directed Acyclic Graphs.” `https://mixtape.scunning.com/03-directed_acyclical_graphs`. citeturn20view0
    * **Hands-on DAGs & adjustment sets (tool you’ll actually use in practice):** DAGitty website + manual. `https://www.dagitty.net/` and `https://www.dagitty.net/manual-3.x.pdf`. citeturn8search2turn8search10
    * **Python causal pipeline step (identification step explained clearly):** DoWhy “Identifying causal effect” docs. `https://www.pywhy.org/dowhy/v0.14/user_guide/causal_tasks/estimating_causal_effects/identifying_causal_effect/index.html`. citeturn7search11
    * **“ID algorithm” notebook (when backdoor/frontdoor aren’t enough):** DoWhy example notebook on ID. `https://www.pywhy.org/dowhy/v0.9/example_notebooks/identifying_effects_using_id_algorithm.html`. citeturn7search3
    * **Reference text for SCM foundations (book-level depth):** entity["book","Causality: Models, Reasoning, and Inference","cambridge 2009"] — Cambridge University Press page. `https://www.cambridge.org/core/books/causality/B0046844FAE10CBF274D4ACBDAEB5F5B`. citeturn8search0
    * **Graph visualization in Python (`NetworkX` drawing reference):** NetworkX drawing docs. `https://networkx.org/documentation/stable/reference/drawing.html`. citeturn24search1

## 🟩 PHASE 2: Experimental & Marketplace Design
*Solving the "Pathao Problem": When data points are not independent.*

### Module 3: Advanced Experimental Design
* **Theory:** SUTVA violations (interference and spillover).
* **Pathao Focus:** Marketplace Equilibrium—how giving a ride to User A reduces bike supply for User B.
* **Technique:** **Switchback Experiments** (Randomization over Time $\times$ Geography blocks).
* **Mathematics:** Cluster-robust variance estimation.
* **Python Strategy:** Designing power analyses for non-i.i.d. data using `Statsmodels`.

* **Topic-wise Reading List (with links):**
    * **Experiments in marketplaces (interference + equilibrium effects + real platform constraints):** “Experimental Design in Marketplaces” (Amazon Science, 2023). `https://assets.amazon.science/d3/c0/57e3c4f748958278aa6fb05e5700/experimental-design-in-marketplaces.pdf`. citeturn2search16
    * **Switchback experiments (core reference with inference + design):** “Design and Analysis of Switchback Experiments” (arXiv). `https://arxiv.org/pdf/2009.00148`. citeturn2search0
    * **Switchback experiments (same work, stable PDF link often used in classes):** HBS working paper PDF. `https://www.hbs.edu/ris/Publication%20Files/WP21-034_20160b13-a86c-4a0d-b6e9-bbae288486c5_c93009c0-8003-43fd-bb1a-012c02d33b98.pdf`. citeturn2search8
    * **Interference/spillovers (formal causal inference framing, survey-style):** “Causal Inference With Interference and Noncompliance…” course note (Harvard/Imai). `https://imai.fas.harvard.edu/research/files/spillover.pdf`. citeturn2search9
    * **Marketplace interference evidence (real randomized meta-experiment):** “Evidence from a Pricing Meta-Experiment on Airbnb” (marketplace interference + implications). `https://felipelobel.com/assets/Marketplace_Interference.pdf`. citeturn2search12
    * **Cluster-robust inference (the standard economics reference):** “A Practitioner’s Guide to Cluster-Robust Inference.” `https://cameron.econ.ucdavis.edu/research/Cameron_Miller_JHR_2015_February.pdf`. citeturn2search2
    * **Python: cluster-robust covariance in `statsmodels` (what to implement):** `RegressionResults.get_robustcov_results` (includes `cov_type='cluster'`, required `groups`, df corrections). `https://www.statsmodels.org/dev/generated/statsmodels.regression.linear_model.RegressionResults.get_robustcov_results.html`. citeturn15view0
    * **Python: baseline power analysis tools in `statsmodels` (what exists out of the box):** statsmodels power & sample size features + `tt_ind_solve_power`. `https://www.statsmodels.org/dev/stats.html` and `https://www.statsmodels.org/stable/generated/statsmodels.stats.power.tt_ind_solve_power.html`. citeturn24search10turn24search6
    * **Modern A/B testing interference methods (ML/CS perspective):** “A/B testing under Interference with Partial Network Information” (PMLR). `https://proceedings.mlr.press/v238/shankar24a/shankar24a.pdf`. citeturn2search15

### Module 4: Quasi-Experimental "Natural" Designs
* **Theory:** Identifying causal signals when you cannot randomize.
* **Topics:** * **Instrumental Variables (IV):** The Wald Estimator (Encouragement designs).
    * **Regression Discontinuity (RDD):** Sharp vs. Fuzzy (e.g., "Gold" status at 50 rides).
    * **Difference-in-Differences (DiD):** Parallel trends and staggered adoption.
* **Python Strategy:** Implementing `Linearmodels` for IV/RDD and `CausalImpact` (BSTS).

* **Topic-wise Reading List (with links):**
    * **RDD (MS-level, applied, diagnostics like density tests/placebos):** Mixtape Chapter 6 “Regression Discontinuity.” `https://mixtape.scunning.com/06-regression_discontinuity`. citeturn19view0
    * **RDD (classic guide to practice; bandwidths, continuity, manipulation checks):** NBER “Regression Discontinuity Designs: A Guide to Practice” PDF. `https://www.nber.org/system/files/working_papers/w13039/w13039.pdf`. citeturn3search0
    * **IV (intuitive + implemented; connects to LATE logic):** Mixtape Chapter 7 “Instrumental Variables.” `https://mixtape.scunning.com/07-instrumental_variables`. citeturn19view1
    * **IV (seminal LATE identification paper—Wald estimator logic lives here):** “Identification of Causal Effects Using Instrumental Variables” PDF. `https://raw.githubusercontent.com/Mixtape-Sessions/Instrumental-Variables/main/Readings/Lecture3/Angrist_Imbens_Rubin_1996.pdf`. citeturn3search6
    * **DiD (applied baseline + intuition):** Mixtape Chapter 9 “Difference-in-Differences.” `https://mixtape.scunning.com/09-difference_in_differences`. citeturn19view2
    * **DiD (serial correlation + inference pitfalls; essential reading):** NBER “How Much Should We Trust Differences-in-Differences Estimates?” PDF. `https://www.nber.org/system/files/working_papers/w8841/w8841.pdf`. citeturn3search1
    * **Staggered adoption fixes (modern identification/aggregation):** “Difference-in-Differences with Multiple Time Periods” (author PDF). `https://psantanna.com/files/Callaway_SantAnna_2020.pdf`. citeturn4search4
    * **Why two-way fixed effects can mislead (Bacon decomposition):** NBER “Difference-in-Differences with Variation in Treatment Timing” PDF. `https://www.nber.org/system/files/working_papers/w25018/w25018.pdf`. citeturn4search6
    * **Synthetic control (fits “single city rollout” logic):** Mixtape Chapter 10 “Synthetic Control.” `https://mixtape.scunning.com/10-synthetic_control`. citeturn19view3
    * **Python IV implementation (practical syntax):** `linearmodels` documentation (IV formulas like `y ~ 1 + [x ~ z]`). `https://bashtage.github.io/linearmodels/iv/examples/using-formulas.html`. citeturn4search15
    * **Python BSTS / causal impact (the foundational method paper):** “Inferring causal impact using Bayesian structural time-series models” PDF. `https://research.google.com/pubs/archive/41854.pdf`. citeturn5search2
    * **Tooling (package docs for practice):** CausalImpact reference page (concepts + assumptions). `https://google.github.io/CausalImpact/CausalImpact.html`. citeturn5search4

## 🟨 PHASE 3: Causal Machine Learning
*The Gold Standard for personalization and high-dimensional data.*

### Module 5: Meta-Learners & Uplift Modeling
* **Theory:** Estimating Heterogeneous Treatment Effects (HTE).
* **Mathematics:** **X-Learner** vs. **T-Learner** (handling unbalanced cohorts).
* **Pathao Application:** Personalized Incentives—Who gets the 50 BDT voucher? (Targeting the "Persuadables").
* **Python Strategy:** `EconML` for Conditional Average Treatment Effect (CATE) estimation.

* **Topic-wise Reading List (with links):**
    * **Meta-learners (the core paper introducing/organizing S/T/X-learner logic):** “Metalearners for Estimating Heterogeneous Treatment Effects using Machine Learning” (PNAS). `https://www.pnas.org/doi/10.1073/pnas.1804597116`. citeturn9search4
    * **Meta-learners (arXiv version if you want the full preprint history):** `https://arxiv.org/abs/1706.03461`. citeturn9search0
    * **CATE & meta-learner API guidance (what to do in code):** EconML “Meta-Learners” documentation. `https://www.pywhy.org/EconML/spec/estimation/metalearners.html`. citeturn16search3
    * **EconML X-learner behavior (unbalanced treatment arms):** `econml.metalearners.XLearner` documentation. `https://www.pywhy.org/EconML/_autosummary/econml.metalearners.XLearner.html`. citeturn16search7
    * **CausalML meta-learner notebook (training/estimation/validation):** `https://causalml.readthedocs.io/en/latest/examples/meta_learners_with_synthetic_data.html`. citeturn16search6
    * **Uplift modeling “what to measure and why” (classic practitioner-style paper):** “Real-World Uplift Modelling…” (Radcliffe). `https://stochasticsolutions.com/pdf/sig-based-up-trees.pdf`. citeturn9search15
    * **PyLift (fast uplift modeling + evaluation tooling):** PyLift GitHub + documentation intro. `https://github.com/rsyi/pylift` and `https://pylift.readthedocs.io/en/latest/introduction.html`. citeturn16search0turn16search20
    * **CausalML “About” (how the package maps to CATE/uplift):** `https://causalml.readthedocs.io/en/latest/about.html`. citeturn1search1

### Module 6: Double Machine Learning (DML)
* **Theory:** Removing high-dimensional bias via "Orthogonalization."
* **Mathematics:** Frisch-Waugh-Lovell Theorem & Neyman-Orthogonality.
    * $\tilde{Y} = Y - E[Y|X]$ (Residualized outcome)
    * $\tilde{T} = T - E[T|X]$ (Residualized treatment)
* **Application:** Estimating price elasticity across 100+ confounding features.
* **Python Strategy:** `CausalForestDML` for robust interval estimation.

* **Topic-wise Reading List (with links):**
    * **The canonical DML paper (orthogonality + cross-fitting + inference):** “Double/Debiased Machine Learning for Treatment and Structural Parameters” PDF. `https://economics.mit.edu/sites/default/files/2022-08/2017.06%20Double%20Debiased%20Machine%20Learning%20for%20Treat.pdf`. citeturn10search0
    * **DML “how it works” in EconML (practical + mathematical bridge):** EconML spec page “Orthogonal/Double Machine Learning.” `https://www.pywhy.org/EconML/spec/estimation/dml.html`. citeturn10search1
    * **Practical DML intro (designed to be readable):** “An Introduction to Double/Debiased Machine Learning” (arXiv). `https://arxiv.org/pdf/2504.08324`. citeturn10search4
    * **Link to causal forests + “local moment equations” view (helps you *understand* CausalForestDML):** “Generalized Random Forests” (arXiv PDF). `https://arxiv.org/pdf/1610.01271`. citeturn9search2
    * **Python estimator details (`CausalForestDML` class reference):** `https://www.pywhy.org/EconML/_autosummary/econml.dml.CausalForestDML.html`. citeturn1search2
    * **Intuitive Python-first explanation of orthogonalization (optional but very helpful):** “Debiased/Orthogonal Machine Learning” chapter in “Causal Inference for the Brave and True.” `https://matheusfacure.github.io/python-causality-handbook/22-Debiased-Orthogonal-Machine-Learning.html`. citeturn10search9

## 🟧 PHASE 4: Temporal Causality & Precision Medicine
*The Research Core: High-frequency sensor data and feedback loops.*

### Module 7: Longitudinal Causality & G-Methods
* **Theory:** Time-varying confounding (When Glucose is both a mediator and a confounder).
* **Mathematics:** **Marginal Structural Models (MSMs)** and Inverse Probability Weighting (IPW) for time-series.
* **CGM Application:** Uncoupling the effect of a "Cheat Meal" from the "Insulin Correction" that followed.
* **Python Strategy:** Time-series causality using `Tigramite`.

* **Topic-wise Reading List (with links):**
    * **Longitudinal causal inference “main book” (MS-level but very deep; Part III):** entity["book","Causal Inference: What If","hernan robins online"] — free PDF (use longitudinal/time-varying chapters). `https://content.sph.harvard.edu/wwwhsph/sites/1268/2024/01/hernanrobins_WhatIf_2jan24.pdf`. citeturn0search0
    * **Marginal structural models (foundational paper + why MSMs exist):** “Marginal Structural Models and Causal Inference in Epidemiology” PDF. `https://content.sph.harvard.edu/wwwhsph/sites/1268/2014/11/Marginal_Structural_Models_and_Causal_Inference_in.11.pdf`. citeturn11search0
    * **IPW primer (conceptual + applied):** “A Primer on Inverse Probability of Treatment Weighting…” (SAGE). `https://journals.sagepub.com/doi/10.1177/2167696815621645`. citeturn11search18
    * **G-computation (conceptual article on the g-formula):** “The g-computation formula” preprint PDF. `https://statnav.wordpress.com/wp-content/uploads/2017/10/g-computation-formula-preprint.pdf`. citeturn11search1
    * **Time-series causal discovery with Tigramite (tool overview):** Tigramite documentation. `https://jakobrunge.github.io/tigramite/`. citeturn1search3
    * **PCMCI method paper (what Tigramite implements; large-scale nonlinear time series):** Science Advances (2019) paper page. `https://www.science.org/doi/10.1126/sciadv.aau4996`. citeturn1search23
    * **PCMCI+ extension (handles contemporaneous links; critical for sensor streams):** PMLR paper PDF. `https://proceedings.mlr.press/v124/runge20a/runge20a.pdf`. citeturn11search19

### Module 8: Causal Discovery (Structure Learning)
* **Theory:** Learning the DAG from observational data.
* **Algorithms:** PC Algorithm, FCI, and LiNGAM (Linear Non-Gaussian Acyclic Model).
* **Warning:** Hypothesis generation vs. Causal confirmation.
* **Application:** Discovering new physiological triggers in raw CGM sensor streams.

* **Topic-wise Reading List (with links):**
    * **Causal discovery foundations (the standard reference book):** entity["book","Causation, Prediction, and Search","mit press 2000"] — full PDF (2nd ed). `https://projects.illc.uva.nl/cil/uploaded_files/inlineitem/Spirtes_Glymour_Scheines_2000_Causation_Prediction_.pdf`. citeturn12search0
    * **Causal inference + structure learning (modern open-access text):** entity["book","Elements of Causal Inference: Foundations and Learning Algorithms","oapen 2017"] — Open Access PDF. `https://library.oapen.org/bitstream/id/056a11be-ce3a-44b9-8987-a6c68fce8d9b/11283.pdf`. citeturn8search3
    * **PC algorithm (high-dimensional consistency results; classic paper):** JMLR PDF. `https://jmlr.org/papers/volume8/kalisch07a/kalisch07a.pdf`. citeturn12search1
    * **FCI family (time-series adaptation context + latent confounding motivation):** “On Causal Discovery from Time Series Data using FCI” PDF. `https://www.researchgate.net/publication/268324455_On_Causal_Discovery_from_Time_Series_Data_using_FCI/links/5a04b1220f7e9bc4078eacc5/DAGitty-A-Graphical-Tool-for-Analyzing-Causal-Diagrams.pdf`. citeturn12search2
    * **LiNGAM (the original method paper):** JMLR PDF. `https://www.jmlr.org/papers/volume7/shimizu06a/shimizu06a.pdf`. citeturn12search3
    * **Time-series causal discovery settings (PCMCI background + assumptions):** Tigramite overview + PCMCI Sci Advances paper. `https://jakobrunge.github.io/tigramite/` and `https://www.science.org/doi/10.1126/sciadv.aau4996`. citeturn1search3turn1search23

## 🟥 PHASE 5: Causal XAI & Validation
*The "Proof of Work" for your research and your job interview.*

### Module 9: Causal Explainable AI (C-XAI)
* **Theory:** Why SHAP/LIME fail under confounding (Correlation vs. Causation in XAI).
* **Mathematics:** **Causal Shapley Values** (Routing feature importance through the DAG).
* **Application:** "Explain why my sugar spiked." Moving from "Feature weights" to "Counterfactual interventions."
* **Python Strategy:** `DiCE` (Diverse Counterfactual Explanations) and `CausalSHAP`.

* **Topic-wise Reading List (with links):**
    * **LIME (baseline XAI method you’re contrasting against):** “Why Should I Trust You?” (LIME) PDF. `https://arxiv.org/pdf/1602.04938`. citeturn6search7
    * **SHAP (baseline feature attribution method you’re contrasting against):** “A Unified Approach to Interpreting Model Predictions” (SHAP) PDF. `https://arxiv.org/pdf/1705.07874`. citeturn6search6
    * **Causal Shapley values (explicit causal-structure-aware attribution):** NeurIPS paper PDF. `https://papers.neurips.cc/paper_files/paper/2020/file/32e54441e6382a7fbacbbbaf3c450059-Paper.pdf`. citeturn6search8
    * **Causal-SHAP style integration of causal discovery + attribution (recent research direction):** “Causal SHAP: Feature Attribution with Dependency Awareness through Causal Discovery” PDF (2025). `https://arxiv.org/pdf/2509.00846`. citeturn6search0
    * **Counterfactual explanations (the standard legal/ML framing referenced widely):** “Counterfactual Explanations Without Opening the Black Box…” PDF. `https://jolt.law.harvard.edu/assets/articlePDFs/v31/Counterfactual-Explanations-without-Opening-the-Black-Box-Sandra-Wachter-et-al.pdf`. citeturn7search0
    * **`DiCE` library (tool you’ll use; emphasis on diversity + feasibility):** DiCE GitHub repo + project page. `https://github.com/interpretml/DiCE` and `https://www.microsoft.com/en-us/research/project/dice/`. citeturn5search3turn5search15
    * **`CausalSHAP` implementation (library you listed; practical code reference):** CausalShap GitHub repository (game-theoretic causal impact framing). `https://github.com/davidrimshnick/CausalShap`. citeturn6search1

### Module 10: Robustness & Refutation
* **Theory:** "Is my result a fluke?" (The Causal Stress Test).
* **Methods:** Placebo Treatments, Random Common Cause, and Sensitivity Analysis (Rosenbaum Bounds).
* **External Validity:** Can we transport a Pathao result from Dhaka to Chittagong?
* **Python Strategy:** `DoWhy.refute_estimate()` workflow.

* **Topic-wise Reading List (with links):**
    * **Refutation workflow (canonical “what to do after estimation” docs):** DoWhy “Refute the obtained estimate.” `https://www.pywhy.org/dowhy/v0.8/user_guide/effect_inference/refute.html`. citeturn1search0
    * **Negative controls & refutation families (how refutation is organized):** DoWhy refutation guide. `https://www.pywhy.org/dowhy/v0.11/user_guide/refuting_causal_estimates/refuting_effect_estimates/index.html`. citeturn1search4
    * **Sensitivity analysis in DoWhy (simulation-based approach to unobserved confounding):** DoWhy sensitivity analysis docs. `https://www.pywhy.org/dowhy/v0.11/user_guide/refuting_causal_estimates/refuting_effect_estimates/sensitivity_analysis/simulation_based.html`. citeturn1search20turn7search11
    * **Rosenbaum sensitivity bounds (classic sensitivity framing to hidden bias):** “Sensitivity Analysis in Observational Studies” (Rosenbaum). `https://www-stat.wharton.upenn.edu/~rosenbap/BehStatSen.pdf`. citeturn7search1
    * **Transportability/external validity theory (formal conditions for moving effects across environments):** “Transportability of Causal Effects: Completeness Results” PDF. `https://cdn.aaai.org/ojs/8232/8232-13-11759-1-2-20201228.pdf`. citeturn7search6
    * **Transportability algorithms (deeper technical reference, often cited):** “A General Algorithm for Deciding Transportability of Causal Effects” PDF. `https://ftp.cs.ucla.edu/pub/stat_ser/r404-reprint.pdf`. citeturn7search2
    * **Meta-transportability (extends transportability ideas):** PMLR paper PDF. `https://proceedings.mlr.press/v31/bareinboim13a.pdf`. citeturn7search14

## 🛠️ The Professional Python Stack
| Category | Libraries |
| :--- | :--- |
| **Orchestration** | `DoWhy` |
| **Estimation** | `EconML`, `CausalML`, `PyLift` |
| **Time-Series** | `Tigramite`, `CausalImpact` |
| **XAI** | `DiCE`, `Shapley` |
| **Quasi-Ex** | `Statsmodels`, `Linearmodels` |
