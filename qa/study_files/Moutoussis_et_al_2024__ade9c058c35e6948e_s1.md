# Moutoussis et al. (2024)

- **study_id:** `ade9c058c35e6948e_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Moutoussis, M., Barnby, J., Durand, A., Croal, M., Dilley, L., Rutledge, R. B., & Mason, L. (2024). Impressions about harm are formed rapidly and then refined, modulated by serotonin. *Social Cognitive and Affective Neuroscience*, *19*(1), nsae078. https://doi.org/10.1093/scan/nsae078
- **citation_short:** Moutoussis et al. (2024)
- **doi:** 10.1093/scan/nsae078
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** Department of Communicative Sciences and Disorders, Michigan State University, East Lansing, MI 48824, United States; Department of Clinical, Educational and Health Psychology, Uinversity College London, London WC1E7HB, United Kingdom; mits unrestricted reuse, distribution, and reproduction in any medium, provided the original work is properly cited; Department of Imaging Neuroscience, University College London, 12 Queen Square, London WC1N 3AR, United Kingdom; Department of Imaging Neuroscience, University College London, London WC1N 3AR, United Kingdom; Department of Psychology, Royal Hollow
- **code_url:** https://github.com/mmoutou/Classify-refine_Sharing_

## Computational level
- **study_focus:** Mentalizing learning / harm attribution learning — how individuals learn to classify and refine attributions of harmful intent vs. self-interest in others' economic decisions, and the modulatory role of serotonin (citalopram).
- **study_focus_short:** Mentalizing learning / harm attribution learning
- **learning_mode_description:** - Learning mode: Learning from observed economic splits about a partner's harmful intent vs. self-interest motives, using a classify-then-refine process.   - Learning from:     - Source type (social): other (dictator partner)     - Source content (social): action/policy (fair vs. unfair economic split decisions)   - Learning about:     - Target type (social): other (dictator partner)     - Target content (social): state (mental state; harmful intent vs. self-interest motives)
- **task_description:** In a modified repeated Dictator Game ("Sharing Game"), participants (receivers) observe four on-screen dictators each making 12 fair (5:5) or unfair (10:0) splits. After each split, participants rate the dictator's likely harmful intent and self-interest, and before each split they report their expectation of a fair outcome.
- **task_paradigm:** Dictator game
- **players:** Single agent (participant as receiver), multi-target (4 dictators; 2 mostly fair, 2 mostly unfair)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Photos of women of varying age and ethnicity (black vs. white), monetary split outcomes (fair 5:5 vs. unfair 10:0)
- **method:** pharmacological / behavioural
- **method_full:** behavioural (with pharmacological manipulation: citalopram vs. placebo, week-long)
- **main_result:** - Main Results:   - Classify-refine model superior to classic learning model (median BIC 372.21 vs. 446.69, Wilcoxon P < 1E-5)   - Model without POC bias preferred over model with POC bias (median BIC 366.2 vs. 372.2, Wilcoxon P = 8.5E-4); only 10/73 participants better fit by bias model   - Average HI attributions increased with subjective SES (β = 0.109, SE = 0.048, P = .030)   - Citalopram did not significantly affect HI attributions (P = .11)   - Modest evidence citalopram enhanced SI attributions (β = 0.269, SE = 0.134, P = .048)   - Citalopram decreased typing confidence parameter aEv (β = −1.18, SE = 0.50, P = .023)   - initHarmInt stability baseline-to-followup (P = .0096, adj. R² = 0.096)   - typingConf stability (P = .00011, adj. R² = 0.21)   - fairnessB stability (P = 1.5E-5, adj. R² = 0.253)
- **effect_size:** - Main Results:   - Classify-refine model superior to classic learning model (median BIC 372.21 vs. 446.69, Wilcoxon P < 1E-5)   - Model without POC bias preferred over model with POC bias (median BIC 366.2 vs. 372.2, Wilcoxon P = 8.5E-4); only 10/73 participants better fit by bias model   - Average HI attributions increased with subjective SES (β = 0.109, SE = 0.048, P = .030)   - Citalopram did not significantly affect HI attributions (P = .11)   - Modest evidence citalopram enhanced SI attributions (β = 0.269, SE = 0.134, P = .048)   - Citalopram decreased typing confidence parameter aEv (β = −1.18, SE = 0.50, P = .023)   - initHarmInt stability baseline-to-followup (P = .0096, adj. R² = 0.096)   - typingConf stability (P = .00011, adj. R² = 0.21)   - fairnessB stability (P = 1.5E-5, adj. R² = 0.253)
- **learning_from:** Other (dictator); observed fair/unfair split decisions (action/policy)
- **learning_about:** Other (dictator); harmful intent vs. self-interest motives (mental states)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Classify-refine active inference HMM (2-state per attribution dimension; 10 params: pHI0, pSI0, dEv, αPrec, wH, wS, w0, λ_other, aEv, ω) — no POC bias, no evidence ratio parameter
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** - {"name": "Classic learning model (6-bin HMM)", "family": "Active inference / HMM", "n_params": "~10-12", "metric": "BIC"} - {"name": "Classify-refine model (full, with POC bias + evidence ratio)", "family": "Active inference / HMM", "n_params": 12, "metric": "BIC"} - {"name": "Classify-refine model (no POC bias, with evidence ratio)", "family": "Active inference / HMM", "n_params": 11, "metric": "BIC"} - {"name": "Classify-refine model (no POC bias, no evidence ratio) — WINNING", "family": "Active inference / HMM", "n_params": 10, "metric": "BIC"} - {"name": "Classify-refine model (with POC bias, no evidence ratio)", "family": "Active inference / HMM", "n_params": 11, "metric": "BIC"}  Note: Exact n_params for classic model not specified in main text; detailed equations stated to be in Supplementary data (not accessible).
- **model_mb_mf:** Bayesian
- **model_params:** - pHI0 (initHarmInt): Central tendency of initial/prior beliefs over harm intent attribution [S] - pSI0 (initSelfInt): Central tendency of initial/prior beliefs over self-interest attribution [S] - dEv (IntentAttrEv): Certainty of prior belief in positive or negative intent attribution - αPrec (decisPrec): Baseline decision precision / inverse temperature - wH (wHarmInt): Weight of harm intent in dictator's policy fairness [S] - wS (wSelfInt): Weight of self-interest in dictator's policy fairness [S] - w0 (fairnessB): Bias (intercept) in dictator's policy fairness function - λ_other: Learning rate from one dictator to the next [S] - aEv (typingConf): Confidence/certainty of prior belief over typing the level of niceness of "positive" and "negative" character classes [S] - ω (learnRetn): Extent of learning retention from trial to trial  Excluded parameters in winning model: - evidRatio (EvRat): Ratio of initial evidence over HI vs. SI — excluded (ratio = 1) - POCbias: Bias for non-white dictators — excluded (bias = 0)  Mean fitted values: Not reported in main text.
- **social_param:** pHI0 (initial harm intent prior), pSI0 (initial self-interest prior), wH (weight of harm intent on fairness), wS (weight of self-interest on fairness), λ_other (cross-dictator learning rate), aEv (typing confidence — how quickly one classifies others as beneficial vs. detrimental)
- **social_param_name:** pHI0
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (corrected for small samples), AIC
- **how_model_fit:** individual-level-fit (MAP estimation with weakly informative priors, adaptive grid-search optimization with multiple initial conditions)
- **data_type_fit_to:** choice behavior (fairness expectations, harm intent ratings, self-interest ratings)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A — no neuroimaging
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 74 enrolled (44 female, 29 male, 1 missing); 42 randomized to citalopram, 32 to placebo; 73 completed baseline, 66 completed follow-up. Young adult sample (median age = 25), highly educated, low income, predominantly BAME backgrounds (most common ethnicities: white and Chinese).
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Task uses ecologically valid photos of diverse women as dictators (improvement over abstract stimuli), but remains a stylized economic game with fictive money. Binary fair/unfair splits limit the range of social behaviors observed. Healthy volunteer sample limits clinical generalizability.
- **eligibility_flag:** 
- **concerns:** No neuroimaging data despite being published in SCAN (a neuroimaging journal). Supplement with detailed model equations and figures not accessible for verification. Healthy sample with no clinically significant symptoms — limits relevance for clinical claims about SSRIs. Short (1-week) SSRI treatment may be insufficient for full pharmacological effects. Sample not representative of UK population (predominantly young, highly educated, BAME women). Multiple statistical tests without full correction for multiple comparisons. Some exploratory findings (citalopram effect on typing confidence) reported at uncorrected P = .023.
- **limitations_reported:** Study did not involve participants with clinically significant symptoms; citalopram had no effect on mood and anxiety measures; absence of detectable biases related to low subjective socioeconomic status or ethnicity needs replication in samples more representative of the general population; mechanisms of serotonergic antidepressant action need to be studied over longer time spans.
- **limitations_categorized:** limited generalizability (healthy sample); limited clinical relevance; sample representativeness; short treatment duration; task simplicity
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - all_models_tested: MEDIUM — exact number of parameters for classic model not stated in main text; detailed model equations in supplement (not accessible) - model_params (mean fitted values): LOW — mean fitted values not reported in main text; may be in supplement - wc_guidelines Rule 3 (simulate): MEDIUM — supplement may contain simulation details but is not accessible - wc_guidelines Rule 5 (parameter recovery): MEDIUM — supplement may contain this but not accessible - wc_guidelines Rule 6 (model recovery): MEDIUM — supplement may contain this but not accessible
- **cannot_find:** - Full model equations (stated to be in Supplementary data) - Mean fitted parameter values - Supplementary Table S1 (prior specifications) - Supplementary Eq. S1 (logistic function details) - Supplementary Figs S1-S8 - Whether simulations, parameter recovery, or model recovery were performed (supplement not accessible)
- **other_notes:** Supplement not accessible — detailed model equations, prior specifications, and supplementary figures/tables are referenced extensively but contained only in the Supplementary data hosted at SCAN online. The paper explicitly states "Detailed explanations and equations follow in the Supplementary data." This means the algorithmic-level extraction may be incomplete. The paper uses active inference framework but notes findings can be implemented in RL frameworks too. The study is primarily behavioral with pharmacological manipulation (not neuroimaging despite being in SCAN). The "classify-refine" hypothesis is the central novel contribution — a 2-state (beneficial/detrimental) rapid classification followed by slower refinement, rather than fine-grained 6-bin learning. GitHub data available at https://github.com/mmoutou/Classify-refine_Sharing_game.
- **re_extract_flag:** false (main text fully accessible; supplement not accessible but main text provides substantial detail)

## Taxonomy / categorization (active codes only)
- pharma_serotonin
- pop_healthy_adults
- rr_pharma_serotonin
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_depth = structural
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_bayesian
- tax_param_learning_rate
- tax_param_precision
- tax_param_social_weight
- tax_popclass_healthy
- tax_popclass_pharmacological
- tax_rr_domain = F_affective_moral
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_F_affective_moral
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_learning_rate
- tax_rr_param_precision
- tax_rr_primary_topic = moral_harm
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_mentalizing
- tax_rr_topic_moral_harm
- tax_topic_mentalizing
- tax_topic_moral_harm
