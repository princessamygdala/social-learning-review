# Feng et al. (2020)

- **study_id:** `a0f14a5ff011d1dc8_s3`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Feng, S., Christopoulos, G., Chiu, P. H., & King-Casas, B. (2020). The effects of oxytocin on self- and other-regarding reinforcement learning. In S. Feng, Self- and other-regarding reinforcement learning: Disruptions in mental disorders and oxytocin's modulating role in healthy people [Doctoral dissertation, Virginia Polytechnic Institute and State University], Paper III, pp. 117-152.
- **citation_short:** Feng et al. (2020)
- **doi:** Not available (unpublished dissertation chapter)
- **publication_type:** thesis
- **year:** 2020.0
- **field_of_study:** Psychology
- **affiliations_raw:** 
- **code_url:** 

## Computational level
- **study_focus:** Effects of oxytocin on self- and other-regarding reinforcement learning in healthy males
- **study_focus_short:** Effects of oxytocin on self- and other-regarding reinforcement learning in
- **learning_mode_description:** - Learning mode: Learning from own and other's monetary outcomes about reward contingencies of abstract patterns for self and an anonymous partner, under oxytocin vs. placebo   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (monetary points for self)     - Source type (social): other (anonymous partner)       - Source content (social): outcome (monetary points for other)   - Learning about:     - Target type (non-social): world (stimulus-reward contingencies for self)       - Target content (non-social): stimulus (abstract pattern values for self)     - Target type (social): other (anonymous partner)       - Target content (social): outcome (abstract pattern values for other)
- **task_description:** In a double-blind, placebo-controlled, within-participant design, healthy males chose between two abstract patterns across six conditions with different self-other allocation structures after intranasal oxytocin or placebo. Each pattern was associated with an 80% probability of a particular monetary allocation for the participant and an anonymous partner (30 trials per condition).
- **task_paradigm:** Prosocial choice task
- **players:** Single agent (participant), dyadic (anonymous partner; passive recipient)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Abstract patterns, monetary point outcomes for self and other
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - OT decreased other-regarding learning rates (mu_slope = -0.93, 95% HDI: [-1.98, -0.04], P = 0.020) - No significant OT effect on self-regarding learning rates or other parameters - Cooperative participants showed decreased SVO-congruent choices after OT in condition 3 (F(1,17) = 4.84, P = 0.042) - Preferred allocations (eta) correlated with SVO (r = 0.48, P = 0.009) - Positive-eta group showed decreased preferred allocations after OT (t(16) = -2.68, P = 0.017) - Other-PE signals in ACC decreased after OT (t(24) = -2.19, P = 0.039) - Self-PE signals in VS not different between drug conditions (t(24) = -0.04, P = 0.80)
- **effect_size:** - OT effect on other-regarding LR: mu_slope = -0.93, 95% HDI [-1.98, -0.04] - SVO ~ eta correlation: r = 0.48 - SVO-congruent choices drug effect: F(1,17) = 4.84 - Positive eta group, OT on eta: t(16) = -2.68 - ACC other-PE, OT vs PL: t(24) = -2.19 - OT effect on other-LR in positive eta group: t(16) = -4.75 - OT effect on other-LR in negative eta group: t(11) = -5.65
- **learning_from:** Self (own monetary outcomes) and other (anonymous partner's monetary outcomes)
- **learning_about:** World (stimulus-reward contingencies for self-other allocations); other (partner's reward contingencies)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Double angle distance model (6 params: alpha_S, alpha_O, beta, eta, kappa_S, kappa_O) - EV_S,t = EV_S,t-1 + alpha_S * ((1 + kappa_S * A_t-1) * V_S,t-1 - EV_S,t-1) - EV_O,t = EV_O,t-1 + alpha_O * ((eta + kappa_O * A_t-1) * V_O,t-1 - EV_O,t-1) - EV_t = EV_S,t + EV_O,t - Softmax: P_a,t = exp(beta * EV_a,t) / [exp(beta * EV_a,t) + exp(beta * EV_b,t)]
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Basic RL model (self-outcomes only)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "iBIC=8897.5, LOOIC=8975.4, WAIC=8974.1"},   {"name": "Gamma model", "family": "Rescorla-Wagner with social preference", "n_params": 4, "metric": "iBIC=8106.3, LOOIC=8216.1, WAIC=8213.3"},   {"name": "Angle distance model", "family": "Rescorla-Wagner with angle distance", "n_params": 5, "metric": "iBIC=7724.2, LOOIC=7886.9, WAIC=7879.6"},   {"name": "Double angle distance model", "family": "Rescorla-Wagner with double angle distance", "n_params": 6, "metric": "iBIC=7715.9, LOOIC=7876.9, WAIC=7868.9"},   {"name": "Fehr-Schmidt model", "family": "Inequality aversion RL", "n_params": 3, "metric": "iBIC=7901.6, LOOIC=8053.7, WAIC=8047.6"},   {"name": "Van Lange model", "family": "Social utility RL", "n_params": 4, "metric": "iBIC=7856.2, LOOIC=8002.5, WAIC=7993.5"} ]
- **model_mb_mf:** MF
- **model_params:** - alpha_S: self-regarding learning rate [0-1]; no OT effect - alpha_O: other-regarding learning rate [0-1] [S]; OT effect: decreased (mu_slope = -0.93) - beta: inverse temperature [>=0]; choice consistency; no OT effect - eta: preferred allocation [-1 to 1] [S]; social preference; OT decreased in cooperative participants - kappa_S: angle distance weight for self [-1 to 1]; no OT effect - kappa_O: angle distance weight for other [-1 to 1] [S]; no OT effect
- **social_param:** eta (preferred allocation) — represents the individual's social preference/cooperativeness. kappa_O (angle distance weight for other) — modulates how discrepancy between preferred and actual allocations influences other-regarding learning. alpha_O (other-regarding learning rate) — rate of learning from other's outcomes.
- **social_param_name:** eta
- **social_param_value:** -0.93
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** iBIC (integrated Bayesian information criterion), LOOIC (leave-one-out cross-validation information criterion), WAIC (widely applicable information criterion)
- **how_model_fit:** individual-level-fit (hierarchical Bayesian estimation using Stan; individual parameters extracted from hierarchical model)
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — trial-by-trial PE values from winning model entered as parametric modulators in GLMs
- **contrast:** - Self-PE parametric modulator at outcome event (VS ROI): no OT effect (t(24) = -0.04, P = 0.80) - Other-PE parametric modulator at outcome event (ACC ROI): OT decreased other-PE signals (t(24) = -2.19, P = 0.039)
- **key_regions:** Other-regarding PE signals in anterior cingulate cortex decreased after oxytocin. Self-regarding PE signals in ventral striatum not affected by oxytocin.
- **key_regions_abbrev:** VS, striatum, ACC
- **coordinates_peak:** - ACC ROI (a priori, from Lockwood et al., 2015 & Apps et al., 2015): 5, 31, 12 - VS ROI: anatomical mask (Oxford-GSK-Imanova atlas) - No whole-brain analysis conducted; only ROI analysis
- **analysis_type:** ROI  ---  ## QUALITY
- **analysis_type_clean:** ROI
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N=29 behavioral (healthy males; age range 18-45, mean = 26.72 +/- 7.27); N=25 imaging (after exclusions for head motion and outlier). Within-participant design (each participant completed both OT and PL conditions).
- **population_category:** healthy adults
- **population_age_range:** 18–45
- **ecological_validity:** Limited — laboratory probabilistic learning task with abstract patterns and monetary points for an anonymous partner. Double-blind placebo-controlled design is a strength. However, anonymous partner reduces social richness. Only males tested.
- **eligibility_flag:** 
- **concerns:** Only male participants. Small sample size (N=29 behavioral, N=25 imaging). Anonymous partner limits ecological validity. Dissertation chapter, not yet peer-reviewed. Same task as Paper II but different population. The social agent (anonymous partner) is passive — participant choices do not lead to interactive dynamics.
- **limitations_reported:** the variations of the four outcomes were relatively small and could not cover all angles in a Cartesian coordinate system"; "the social partner in the task was an anonymous person. Whether social familiarity would modulate OT's effects was not specifically examined"; "we only recruited males; therefore, the effects of OT on learning for others in females are yet to be explored in future research
- **limitations_categorized:** task simplicity (limited outcome range); limited ecological validity (anonymous partner); limited generalizability (males only); sample size
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
- **flagged_fields:** - doi: LOW — not available for unpublished dissertation - effect_size: MEDIUM — Bayesian HDIs reported rather than traditional effect sizes - model_params mean fitted values: MEDIUM — group-level means shown in figures but not tabulated - preregistered: MEDIUM — not mentioned
- **cannot_find:** Exact mean fitted parameter values per condition (shown only in figures); DOI
- **other_notes:** This is Paper III from a doctoral dissertation. Uses the same probabilistic social learning task and double angle distance model as Paper II, but applied to a healthy sample with an oxytocin manipulation. The study provides causal evidence (via pharmacological manipulation) that OT attenuates other-regarding learning and decreases cooperativeness. No supplement file was found separately; supplementary information is embedded within the dissertation text.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pharma_oxytocin
- pop_healthy_adults
- rr_pharma_oxytocin
- rr_pop_healthy_adults
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
- tax_popclass_healthy
- tax_popclass_pharmacological
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_secondary_topic = empathy_vicarious
- tax_rr_topic_empathy_vicarious
- tax_rr_topic_prosocial_altruism
- tax_topic_empathy_vicarious
- tax_topic_prosocial_altruism
