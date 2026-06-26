# Feng et al. (2020)

- **study_id:** `a0f14a5ff011d1dc8_s2`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Feng, S., Christopoulos, G., Julien, J., Chiu, P. H., & King-Casas, B. (2020). Self- and other-regarding reinforcement learning in post-traumatic stress disorder with and without comorbid depression. In S. Feng, Self- and other-regarding reinforcement learning: Disruptions in mental disorders and oxytocin's modulating role in healthy people [Doctoral dissertation, Virginia Polytechnic Institute an
- **citation_short:** Feng et al. (2020)
- **doi:** Not available (unpublished dissertation chapter)
- **publication_type:** thesis
- **year:** 2020.0
- **field_of_study:** Psychology
- **affiliations_raw:** 
- **code_url:** 

## Computational level
- **study_focus:** Other-regarding reinforcement learning in PTSD; self- and other-regarding reward learning in combat-exposed veterans with PTSD with and without comorbid depression
- **study_focus_short:** Other-regarding reinforcement learning in PTSD
- **learning_mode_description:** - Learning mode: Learning from own and other's monetary outcomes about reward contingencies of abstract patterns for self and an anonymous partner   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (monetary points for self)     - Source type (social): other (anonymous partner)       - Source content (social): outcome (monetary points for other)   - Learning about:     - Target type (non-social): world (stimulus-reward contingencies for self)       - Target content (non-social): stimulus (abstract pattern values for self)     - Target type (social): other (anonymous partner)       - Target content (social): outcome (abstract pattern values for other)
- **task_description:** Participants chose between two abstract patterns across six conditions with different self-other allocation structures. Each pattern was associated with an 80% probability of a particular monetary allocation for the participant and an anonymous partner (30 trials per condition, 180 total).
- **task_paradigm:** Prosocial choice task
- **players:** Single agent (participant), dyadic (anonymous partner; passive recipient)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Abstract patterns, monetary point outcomes for self and other
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - PTSD was associated with decreased other-regarding learning rates (mu_slope1 = -2.56, 95% HDI: [-4.01, -1.31], P < 0.001) - Comorbid depression was associated with increased self-regarding learning rates (mu_slope2 = 0.81, HDI: [0.29, 1.34], P = 0.001) - Other-regarding surprise signals in right IPL were higher in depressed PTSD than controls (F(2,48) = 3.98, P = 0.025; DP > HC: t = -2.60, P = 0.012) - IPL surprise signals negatively correlated with other-regarding learning rate (r = -0.30, P = 0.026) and positively with avoidance & numbing (r = 0.30, P = 0.025) - No group differences in self-PE signals in ventral striatum (F(2,48) = 0.32, P = 0.73) or other-PE signals in ACC (F(2,48) = 0.07, P = 0.93)
- **effect_size:** - PTSD effect on other-regarding LR: mu_slope = -2.56, 95% HDI [-4.01, -1.31] - Depression effect on self-regarding LR: mu_slope = 0.81, HDI [0.29, 1.34] - IPL surprise group difference: F(2,48) = 3.98 - IPL surprise ~ other-LR: r = -0.30 - IPL surprise ~ avoidance & numbing: r = 0.30
- **learning_from:** Self (own monetary outcomes) and other (anonymous partner's monetary outcomes)
- **learning_about:** World (stimulus-reward contingencies for self-other allocations); other (partner's reward contingencies)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Double angle distance model (5 params: alpha_S, alpha_O, beta, eta, kappa_S, kappa_O) - EV_S,t = EV_S,t-1 + alpha_S * ((1 + kappa_S * A_t-1) * V_S,t-1 - EV_S,t-1) - EV_O,t = EV_O,t-1 + alpha_O * ((eta + kappa_O * A_t-1) * V_O,t-1 - EV_O,t-1) - EV_t = EV_S,t + EV_O,t - Softmax: P_a,t = exp(beta * EV_a,t) / [exp(beta * EV_a,t) + exp(beta * EV_b,t)]
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Basic RL model (self-outcomes only)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "iBIC=12070.1, LOOIC=12167.4, WAIC=12166.3"},   {"name": "Gamma model", "family": "Rescorla-Wagner with social preference", "n_params": 4, "metric": "iBIC=11208.3, LOOIC=11354.8, WAIC=11352.1"},   {"name": "Angle distance model", "family": "Rescorla-Wagner with angle distance", "n_params": 5, "metric": "iBIC=10713.5, LOOIC=10965.8, WAIC=10970.6"},   {"name": "Double angle distance model", "family": "Rescorla-Wagner with double angle distance", "n_params": 6, "metric": "iBIC=10693.2, LOOIC=10844.4, WAIC=10839.9"},   {"name": "Fehr-Schmidt model", "family": "Inequality aversion RL", "n_params": 3, "metric": "iBIC=11091.5, LOOIC=11277.1, WAIC=11272.6"},   {"name": "Van Lange model", "family": "Social utility RL", "n_params": 4, "metric": "iBIC=11007.4, LOOIC=11167.8, WAIC=11161.8"} ]
- **model_mb_mf:** MF
- **model_params:** - alpha_S: self-regarding learning rate [0-1]; depression effect: increased (mu_slope2 = 0.81) - alpha_O: other-regarding learning rate [0-1] [S]; PTSD effect: decreased (mu_slope1 = -2.56) - beta: inverse temperature [>=0]; choice consistency - eta: preferred allocation [-1 to 1] [S]; social preference parameter reflecting cooperativeness/competitiveness - kappa_S: angle distance weight for self [-1 to 1]; modulates self-outcome transformation - kappa_O: angle distance weight for other [-1 to 1] [S]; modulates other-outcome transformation
- **social_param:** eta (preferred allocation) — represents the individual's social preference/cooperativeness, transforming other's outcomes into subjective value. kappa_O (angle distance weight for other) — modulates how the discrepancy between preferred and actual allocations influences other-regarding learning. alpha_O (other-regarding learning rate) — rate of learning from other's outcomes.
- **social_param_name:** eta
- **social_param_value:** -2.56
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** iBIC (integrated Bayesian information criterion), LOOIC (leave-one-out cross-validation information criterion), WAIC (widely applicable information criterion)
- **how_model_fit:** individual-level-fit (hierarchical Bayesian estimation using Stan; individual parameters extracted from hierarchical model)
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — trial-by-trial PE values from winning model entered as parametric modulators in GLMs
- **contrast:** - Self-PE parametric modulator at outcome event (VS ROI) - Other-PE parametric modulator at outcome event (ACC ROI) - Other-regarding surprise (unsigned other-PE) parametric modulator at outcome event (whole-brain + IPL ROI) - Group differences: DP > NP > HC in right IPL surprise signals (F(2,48) = 3.98, P = 0.025)
- **key_regions:** Other-regarding surprise signals in bilateral inferior parietal lobule; right middle frontal gyrus; bilateral supplementary motor area. Self-PE signals in ventral striatum (no group differences). Other-PE signals in ACC (no group differences). IPL surprise signals correlated with avoidance & numbing and negatively with other-regarding learning rate.
- **key_regions_abbrev:** VS, striatum, ACC, MFG, parietal, SMA
- **coordinates_peak:** - R Inferior parietal lobule (peak): 48, -51, 48 - R Middle frontal gyrus: 45, 39, 27 - R/L Supplementary motor area: 6, 21, 45 - L Inferior parietal lobule: -42, -45, 42 - ACC ROI (a priori, from Lockwood et al., 2015 & Apps et al., 2015): 5, 31, 12 - VS ROI: anatomical mask (Oxford-GSK-Imanova atlas)
- **analysis_type:** both (whole-brain for surprise signals + ROI for self-PE in VS, other-PE in ACC, surprise in IPL)  ---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N=74 behavioral (15 HC, 29 NP nondepressed PTSD, 30 DP depressed PTSD); N=60 imaging (after motion exclusions); N=55 in group comparisons controlling for combat exposure (12 HC, 19 NP, 24 DP). Combat-exposed US military veterans; predominantly male (7 females total); ages 18-65, mean ~34.
- **population_category:** mixed
- **population_age_range:** 18–65
- **ecological_validity:** Limited — laboratory probabilistic learning task with abstract patterns and monetary points for an anonymous partner; does not capture real-world social learning. However, the use of real monetary outcomes for self and other, and the veteran clinical sample, add some ecological relevance.
- **eligibility_flag:** 
- **concerns:** Predominantly male veteran sample limits generalizability. No depression-only group prevents full factorial analysis of PTSD vs. depression effects. Dissertation chapter, not yet peer-reviewed journal article. Medication status varied across groups and may confound results. Small HC group (N=15).
- **limitations_reported:** Since it is correlational rather than causal, we cannot exclude the possibility that the impaired social learning predisposes to PTSD initiation"; "our participants did not include a depression only group, preventing us from testing PTSD and depression as two separate factors"; "our participants were predominantly males and all were veterans; therefore, our findings are yet to be replicated in females or other populations in future research
- **limitations_categorized:** correlational design; missing control group (no depression-only); limited generalizability (predominantly male veterans); sample composition
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** No
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - doi: LOW — not available for unpublished dissertation - effect_size: MEDIUM — Bayesian HDIs reported rather than traditional effect sizes; correlation coefficients reported - model_params mean fitted values: MEDIUM — group-level means shown in figures but exact fitted values per parameter not tabulated in accessible text - preregistered: MEDIUM — not mentioned, assumed not preregistered
- **cannot_find:** Exact mean fitted parameter values for each group (shown only in figures); DOI
- **other_notes:** This is Paper II from a doctoral dissertation. The double angle distance model is a novel contribution that extends Christopoulos & King-Casas (2015) by incorporating dynamic social preference transformation based on angle distances between preferred and actual allocations. The supplementary information is included within the dissertation text itself.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_depression
- pop_healthy_adults
- pop_ptsd_trauma
- rr_pop_depression
- rr_pop_healthy_adults
- rr_pop_ptsd_trauma
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = shared
- spec_source = social
- spec_target = partly
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_secondary_topic = empathy_vicarious
- tax_rr_topic_empathy_vicarious
- tax_rr_topic_prosocial_altruism
- tax_topic_empathy_vicarious
- tax_topic_prosocial_altruism
