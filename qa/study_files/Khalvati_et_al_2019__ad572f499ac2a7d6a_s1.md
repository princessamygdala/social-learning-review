# Khalvati et al. (2019)

- **study_id:** `ad572f499ac2a7d6a_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Khalvati, K., Park, S. A., Mirbagheri, S., Philippe, R., Sestito, M., Dreher, J.-C., & Rao, R. P. N. (2019). Modeling other minds: Bayesian inference explains human choices in group decision-making. *Science Advances*, *5*(11), eaax8783. https://doi.org/10.1126/sciadv.aax8783
- **citation_short:** Khalvati et al. (2019)
- **doi:** 10.1126/sciadv.aax8783
- **publication_type:** peer-reviewed journal
- **year:** 2019.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Center for Mind and Brain, University of California, Davis, Davis, observations, and a simulation of the future based on the current; Laboratory, Institut des Sciences Cognitives Marc actions for modeling human decisions within a group; School of Computer Science and Engineering, University of Washington, current choices; ethods and human behavior when the subject inter-; laboratory setting, we used the
- **code_url:** 

## Computational level
- **study_focus:** Cooperation learning / group decision-making — modeling the "mind of the group" via Bayesian inference in a volunteer's dilemma (public goods game)
- **study_focus_short:** Cooperation learning / group decision-making
- **learning_mode_description:** - Learning mode: Learning from anonymous group contribution outcomes about the group's cooperativeness to guide own contribution decisions   - Learning from:     - Source type (social): group (anonymous group members)     - Source content (social): outcomes (total number of contributions and success/failure of public goods generation)   - Learning about:     - Target type (social): group (average group member)     - Target content (social): state (mental state; cooperativeness / average probability of contribution)
- **task_description:** In a multiround binary public goods game (volunteer's dilemma), participants in groups of 5 decided each round whether to contribute 1 monetary unit or free-ride; public goods (2 MU to each player) were generated only if at least k players (k=2 or k=4) contributed. After each round, the total number of contributions and success/failure were revealed, but individual actions remained anonymous.
- **task_paradigm:** Public goods game
- **players:** Single agent (participant), multi-target (4 other ostensible group members, actually computer-simulated)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract monetary decision task; binary choice (contribute/free-ride); numerical feedback (contribution counts, success/failure)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Contribution rate significantly higher for k=4 (M=55%) vs k=2 (M=33%) (t(28)=3.94, d not reported)   - Success rate significantly higher for k=2 (M=87%) vs k=4 (M=36%) (t(28)=10.08, d not reported)   - POMDP fitting accuracy 84% (SD=0.06), LOOCV accuracy 77% (SD=0.08)   - POMDP significantly outperformed Q-learning on fitting accuracy (t(28)=-6.75)   - POMDP significantly outperformed Q-learning on LOOCV accuracy (t(28)=2.20)   - POMDP significantly outperformed descriptive two-factor model on fitting (t(28)=-4.86)   - POMDP significantly outperformed descriptive two-factor model on LOOCV (t(28)=-7.61)   - POMDP success prediction accuracy 71% (SD=0.07)   - Contribution rate declined across rounds for k=4 (first 5 rounds M=0.60 vs last 5 M=0.49; t(28)=3.65)
- **effect_size:** Effect sizes (Cohen's d, r, etc.) not reported; only t-statistics and p-values provided. Accuracy differences: POMDP vs Q-learning fitting 95% CI [0.03, 0.06]; POMDP vs Q-learning LOOCV 95% CI [0.004, 0.08]; POMDP vs two-factor fitting 95% CI [0.03, 0.08]; POMDP vs two-factor LOOCV 95% CI [0.22, 0.38].
- **learning_from:** Group (anonymous); total number of contributions and round outcome (success/failure)
- **learning_about:** Group; average cooperativeness (probability of contribution by an average group member)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** POMDP with Bayesian belief updating over group cooperativeness (Beta(alpha_1, beta_1) prior; decay rate gamma; 3 free params: alpha_1, beta_1, gamma)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** [   {"name": "POMDP (Bayesian belief updating)", "family": "Bayesian/POMDP", "n_params": 3, "metric": "round-by-round accuracy + LOOCV"},   {"name": "Q-learning (model-free RL)", "family": "Q-learning", "n_params": 5, "metric": "round-by-round accuracy + LOOCV"},   {"name": "Linear two-factor descriptive model", "family": "Logistic regression (descriptive)", "n_params": 3, "metric": "round-by-round accuracy + LOOCV"},   {"name": "POMDP without belief update (prior only)", "family": "Bayesian/POMDP (static)", "n_params": 3, "metric": "round-by-round accuracy"},   {"name": "I-POMDP (interactive POMDP)", "family": "Bayesian/I-POMDP", "n_params": "not specified (in supplement)", "metric": "compared in Supplementary Materials"} ]
- **model_mb_mf:** MB (model-based / Bayesian)
- **model_params:** - $\alpha_1$ [S]: Prior parameter for expected contributions (Beta distribution alpha); fitted integer values 1-200; mean across subjects mostly 40-120 range (as ($\alpha_1 + \beta_1$)/2) - $\beta_1$ [S]: Prior parameter for expected free-rides (Beta distribution beta); fitted integer values 1-200 - $\gamma$: Decay rate controlling weight of past vs. recent observations; range [0,1] with precision 0.01; median=0.97, mean=0.93 across subjects - $z$: Softmax temperature (one per k condition, fit across all subjects to maximize choice probability likelihood; does not affect accuracy)
- **social_param:** $\alpha_1$ and $\beta_1$ — prior beliefs about group cooperativeness (expected ratio of contributions to free-rides by group members); $\gamma$ — decay rate determining weight given to recent vs. past social observations
- **social_param_name:** $\alpha_1$
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Round-by-round prediction accuracy (fitting accuracy) + leave-one-out cross-validation (LOOCV) accuracy (each left-out data point = one full game); paired t-tests between models
- **how_model_fit:** individual-level-fit (grid search over integer values for $\alpha_1$, $\beta_1$ [1-200] and $\gamma$ [0.01-1.0 in steps of 0.01]; maximizing round-by-round accuracy)
- **data_type_fit_to:** choice behavior (binary contribute/free-ride decisions per round)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study only)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N=29 (30 recruited, 1 dropped due to anxiety; mean age 22.97 +/- 0.37 years; 14 women; all right-handed)
- **population_category:** healthy adults
- **population_age_range:** M=22.97
- **ecological_validity:** Lab-based economic game with computer-simulated partners (participants believed they were playing with real humans). Abstract monetary incentives; limited ecological validity as real-world group decisions involve richer social cues, non-anonymous interactions, and varied group sizes. However, the volunteer's dilemma paradigm captures a meaningful real-world social dilemma (e.g., bystander intervention, blood donation).
- **eligibility_flag:** 
- **concerns:** Participants played with computer-simulated partners, not real humans, which may alter social reasoning; the authors mention this but the deception could affect generalizability. No neuroimaging data despite the paper's framing as relevant to social neuroscience. Effect sizes (Cohen's d, eta-squared, etc.) are not reported — only t-statistics and CIs. The I-POMDP comparison is relegated entirely to supplement (which is not accessible as a separate file). No parameter recovery or model recovery analyses reported.
- **limitations_reported:** Mimicking human behavior does not guarantee that a POMDP model (or any model) is being implemented in the brain"; model based on binomial/beta distributions specific to binary task structure; framework assumes same prior across games for each subject; no exploration-exploitation trade-off modeled; extension to non-anonymous settings would incur significant computational cost; data and code available upon request only (not openly shared)
- **limitations_categorized:** model validity/neural plausibility; task simplicity; limited generalizability; no exploration modeling; computational scalability; limited data sharing
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - effect_size: LOW — standard effect sizes (Cohen's d, etc.) not reported; only t-statistics and CI differences available - wc_guidelines rule 3 (simulate): MEDIUM — supplement Fig. S2 referenced but supplement not separately accessible; main text shows model predictions vs data but unclear if pre-fitting simulations were performed - model_params (mean fitted values): MEDIUM — exact mean fitted values for $\alpha_1$ and $\beta_1$ not reported; only distributional ranges shown in histograms (Fig. 6) - I-POMDP comparison: LOW — stated as being in Supplementary Materials which is not available as a separate file
- **cannot_find:** - Supplement file (referenced as available at Science Advances website but not in papers folder) — I-POMDP comparison details, Fig. S1, Fig. S2 - Standard effect sizes (Cohen's d, eta-squared, etc.) — not reported in paper - Exact mean fitted parameter values for $\alpha_1$ and $\beta_1$ — only histogram distributions shown
- **other_notes:** The supplementary materials are referenced (Supplementary Text, Fig. S1, Fig. S2) but no supplement file was found in the papers folder. The paper is purely behavioural — no neuroimaging — but discusses implications for neuroimaging and computational psychiatry. The softmax parameter z was fit per k condition across all subjects (not per subject), so it functions as a group-level parameter for choice probability estimation rather than a subject-level free parameter. The computer-simulated opponents used parameters calibrated from a separate PGG study (Park et al., 2013). Note: Supplement not accessible.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MB
- tax_model_bayesian
- tax_param_decay
- tax_param_learning_rate
- tax_param_precision
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = cooperation
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_cooperation
- tax_rr_topic_mentalizing
- tax_topic_cooperation
- tax_topic_mentalizing
