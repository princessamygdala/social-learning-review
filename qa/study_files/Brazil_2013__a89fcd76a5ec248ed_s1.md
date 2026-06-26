# Brazil (2013)

- **study_id:** `a89fcd76a5ec248ed_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Brazil, I. A. (2013). *Change doesn't come easy: Dynamics of adaptive behavior in psychopathy* [Doctoral dissertation, Radboud University Nijmegen]. ISBN 978-94-91027-76-5.
- **citation_short:** Brazil (2013)
- **doi:** N/A (Dissertation; handle: https://hdl.handle.net/2066/115727)
- **publication_type:** thesis
- **year:** 2013.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** University of Amsterdam, the Netherlands) Chapter 4 A neurophysiological dissociation between monitoring one’s own 55; etherlands) and others’ actions in psychopathy; etherlands) Chapter 1 Introduction 7; University, the Netherlands); etherlands Organization for; college van decanen; etherlands); mitted,
- **code_url:** 

## Computational level
- **study_focus:** Social information use during associative learning; computational phenotyping of psychopathy-related traits - Confidence: HIGH
- **study_focus_short:** Social information use during associative learning
- **learning_mode_description:** - Learning mode: Learning from reward history and social advice to make optimal choices in a probabilistic reward task   - Learning from:     - Source type (non-social): world       - Source content (non-social): outcome (reward history — probability of green/blue being correct)     - Source type (social): other (confederate/social partner)       - Source content (social): action/policy (advice about which option to choose)   - Learning about:     - Target type (non-social): world       - Target content (non-social): state (probability of reward for each option)     - Target type (social): other (confederate)       - Target content (social): state (mental state; reliability/trustworthiness of advice) - Confidence: HIGH
- **task_description:** Participants completed 290 trials of a decision-making task choosing between two colored rectangles (blue/green) to accumulate points, learning about reward probabilities from outcome history while simultaneously learning the reliability of advice from a social partner (experimenter, behind a screen). Reward probabilities and advice fidelity varied independently and underwent several reversals. - Confidence: HIGH
- **task_paradigm:** Advice-taking task
- **players:** Single agent (participant), dyadic (confederate partner / experimenter) - Confidence: HIGH
- **n_players:** dyadic (2)
- **partner_type:** confederate
- **stimuli:** Colored rectangles (blue/green) with point values (1–100), social advice (red box around partner's recommended choice), score bar with silver/gold targets - Confidence: HIGH
- **method:** behavioural
- **method_full:** behavioural - Confidence: HIGH
- **main_result:** - Main Results:   - Use of reward-history information (γ_reward_history) negatively correlated with Stress Immunity (r = -0.37, p = 0.018) and Fearlessness (r = -0.35, p = 0.028)   - Use of social advice information (γ_social) negatively correlated with Social Potency (r = -0.33, p = 0.037) and Coldheartedness (r = -0.32, p = 0.046)   - The two computational parameters were uncorrelated (r = 0.067, p = 0.68), indicating independent modulation   - Psychopathy-specific traits (PPI-I: Fearless Dominance) were selectively related to computational parameters; antisociality traits (PPI-II) were not   - Above-chance performance confirmed participants actively learned (mean points earned = 10,364 vs. guessing = 7,276; t(39) = -23.5, p < 0.001) - Confidence: HIGH
- **effect_size:** - γ_reward_history ~ Stress Immunity: r = -0.37 - γ_reward_history ~ Fearlessness: r = -0.35 - γ_social ~ Social Potency: r = -0.33 - γ_social ~ Coldheartedness: r = -0.32 - γ_reward_history ~ γ_social: r = 0.067 (n.s.) - Confidence: HIGH
- **learning_from:** Other (social partner's advice) + world (reward outcome history) - Confidence: HIGH
- **learning_about:** World (reward probabilities for each option) + other (reliability of partner's advice) - Confidence: HIGH  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** Bayesian RL with subjective probability transform (3 params: γ_reward_history, γ_social, β) - Confidence: HIGH
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning / Belief updating
- **all_models_tested:** Only one model was fit; no model comparison was conducted. [{"name": "Bayesian RL with subjective probability transform", "family": "Bayesian RL", "n_params": 3, "metric": "N/A — single model"}] - Confidence: HIGH
- **model_mb_mf:** Bayesian - Confidence: HIGH
- **model_params:** - γ_reward_history: Subjective probability amplification parameter for reward history information; controls how much the objective RL-estimated reward probability influences choice. Range = 0.42–12.9. No [S]. - γ_social [S]: Subjective probability amplification parameter for social advice information; controls how much the RL-estimated advice fidelity influences choice. Range = 1.57–25.2. - β: Temperature/softmax parameter capturing choice stochasticity. No reported mean. - Note: Learning rate is NOT a free parameter — it varies through the task via the Bayesian RL model (Behrens et al., 2007), adapting to volatility. - Confidence: HIGH
- **social_param:** γ_social — Parameterizes the degree to which subjects use social advice information (confederate reliability) to guide their decisions. Higher values = more amplification of social information toward extremes. - Confidence: HIGH
- **social_param_name:** γ_social
- **social_param_value:** 0.42
- **social_param_sd:** 
- **social_param_range:** 0.42–12.9
- **model_comparison_metric:** N/A — only one model tested - Confidence: HIGH
- **how_model_fit:** individual-level-fit (Bayesian estimation procedure in MATLAB, per subject) - Confidence: HIGH
- **data_type_fit_to:** choice behavior - Confidence: HIGH  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none - Confidence: HIGH
- **contrast:** N/A (behavioral study) - Confidence: HIGH
- **key_regions:** N/A (behavioral study) - Confidence: HIGH
- **coordinates_peak:** N/A (behavioral study) - Confidence: HIGH
- **analysis_type:** N/A (no neuroimaging) - Confidence: HIGH  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 40 (36 females, 4 males; non-clinical sample; ages mean = 23.9, SD = 8.5; recruited from N = 485 PPI screening pool; 26 from top/bottom PPI quartiles, 14 from middle quartiles) - Confidence: HIGH
- **population_category:** clinical
- **population_age_range:** 
- **ecological_validity:** Limited — confederate was actually computer-generated advice presented as human partner behind a screen. Task is a stylized probabilistic learning paradigm, not a naturalistic social interaction. Non-clinical sample using self-report psychopathy measure (PPI) rather than diagnosed clinical psychopathy. - Confidence: HIGH
- **eligibility_flag:** 
- **concerns:** - Only one computational model was fit; no model comparison or alternative models tested - No parameter recovery reported - No model recovery reported - No simulation reported - Sample is predominantly female (36/40) in a study about psychopathy — authors acknowledge this as a potential limitation but argue convergence with male clinical samples - Non-clinical sample with self-report measure (PPI) — may not generalize to clinical psychopathy - The "social partner" was actually computer-generated advice, not a real social interaction - Lasso variable selection approach may be underpowered with N = 40 and 8 predictors - Confidence: HIGH
- **limitations_reported:** One potential caveat is that we used learning rates produced by our model in this experiment"; sample consisted predominantly of female participants and findings might not extend to male population; non-clinical population with PPI cannot be equated with clinical psychopathy assessed with PCL-R; future studies needed to confirm whether altered use of information is specific to clinical psychopathy Factor 1. - Confidence: HIGH
- **limitations_categorized:** limited generalizability (non-clinical sample); gender imbalance; task simplicity; no model comparison; limited ecological validity - Confidence: HIGH
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 4.0
- **wc_total:** 4.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_comparison_metric: LOW — only one model tested, no comparison metric applicable - wc_guidelines Rules 2, 3, 5, 6, 7: enforced as No due to single model, no simulation, no recovery - β parameter mean: MEDIUM — range not reported, no group-level mean provided - Confidence ratings as marked above
- **cannot_find:** - Mean fitted values for γ_reward_history, γ_social, and β (only ranges reported for γ parameters) - Model comparison with alternative models - Simulation/parameter recovery results - No supplement was found for this dissertation
- **other_notes:** - This is a doctoral dissertation. Only Chapter 6 (Study 5) meets all inclusion criteria (computational modeling + social learning over time + human behavioral data). Chapters 2–5 and 7 do not use computational modeling. - Chapter 6 was submitted as: Brazil, I.A., Hunt, L.H., Bulten, B.H., Kessels, R.P.C., de Bruijn, E.R.A., Mars, R.B. "Psychopathy-related traits and the use of reward and social information: A computational approach." — potential duplicate check needed against published version. - The Bayesian RL component uses the Behrens et al. (2007) volatility-sensitive learning rate model; γ parameters on top of this are the novel contribution. - Supplement not accessible (none found for this dissertation).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- pop_psychopathy
- rr_pop_healthy_adults
- rr_pop_psychopathy
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- spec_target = partly
- tax_domain_A_influence_transmission
- tax_mod_experiential
- tax_mod_instructed
- tax_model_bayesian
- tax_model_rescorla_wagner
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_topic_social_info_use
- tax_topic_social_info_use
