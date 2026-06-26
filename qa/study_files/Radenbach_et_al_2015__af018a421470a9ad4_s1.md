# Radenbach et al. (2015)

- **study_id:** `af018a421470a9ad4_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Radenbach, C., Reiter, A. M. F., Engert, V., Sjoerds, Z., Villringer, A., Heinze, H.-J., Deserno, L., & Schlagenhauf, F. (2015). The interaction of acute and chronic stress impairs model-based behavioral control. *Psychoneuroendocrinology*, *53*, 268–280.
- **citation_short:** Radenbach et al. (2015)
- **doi:** 10.1016/j.psyneuen.2014.12.017
- **publication_type:** peer-reviewed journal
- **year:** 2015.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Department of Social Neuroscience, Max Planck Institute for Human Cognitive and Brain Sciences, 04103; Department of Neurology, Max Planck Institute for Human Cognitive and Brain Sciences, 04103 Leipzig,; Department of Behavioral Neurology, Leibniz Institute for Neurobiology, 39118 Magdeburg, Germany; Department of Psychiatry and Psychotherapy, Campus Charité Mitte, Charité — Universitätsmedizin; Institute for Human Cognitive and Brain Sciences, Stephanstrasse 1a, 04103 Leipzig, Germany; Department of Neurology, Otto-von-Guericke University, 39120 Magdeburg, Germany; School of Mind & Brain Ins
- **code_url:** 

## Computational level
- **study_focus:** Stress and model-based vs. model-free behavioral control; interaction of acute and chronic stress on goal-directed decision-making
- **study_focus_short:** Stress and model-based vs. model-free behavioral control
- **learning_mode_description:** - Learning mode: Learning from reward outcomes in a sequential decision task about stimulus-reward contingencies and transition structure, under stress manipulation.   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (monetary reward/no reward)   - Learning about:     - Target type (non-social): world (stimulus-reward contingencies and state transition structure)     - Target content (non-social): action/policy (optimal first-stage choice to maximize second-stage reward)
- **task_description:** Participants performed a two-stage Markov sequential decision task (Daw et al., 2011) in which they chose between two first-stage stimuli that probabilistically transitioned (70%/30%) to one of two second-stage stimulus pairs, where a second choice was rewarded (20 cents) according to slowly drifting Gaussian random walks. They performed the task under both an acute psychosocial stress condition (TSST) and a control condition in a within-subjects design.
- **task_paradigm:** Two-step task
- **players:** Single agent (participant), no social target in task itself; between-condition manipulation (stress vs. control)
- **n_players:** single agent (1)
- **partner_type:** none
- **stimuli:** Chinese characters on colored boxes; binary monetary feedback (20 cents or nothing)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Hybrid model best fit in both conditions (XP = 0.99 in both stress and control) - No direct effect of acute stress on omega (balance parameter): t = 0.01, p = 0.990, d = 0.011 - Acute stress increased choice stochasticity at first stage: beta_1 lower under stress (t = 2.60, p = 0.014, d = 0.427) - Acute stress reduced eligibility trace lambda (t = 2.08, p = 0.046, d = 0.424) - Cortisol reactivity negatively correlated with omega during stress (r = -0.46, p = 0.004) - Arousal reactivity positively correlated with omega during stress (r = 0.406, p = 0.010) - Chronic life stress (24 months) predicted stress-induced reduction in omega (Beta = -0.622, t = -2.93, p = 0.007)
- **effect_size:** - Cortisol stress effect: d = 3.001 (peak cortisol stress vs. control) - Heart rate increase stress effect: d = 0.983 - Acute stress on beta_1: d = 0.427 - Acute stress on lambda: d = 0.424 - Acute stress on omega: d = 0.011 (n.s.) - Cortisol-omega correlation: r = -0.46 - Arousal-omega correlation: r = 0.406 - Chronic stress Beta on delta-omega: Beta = -0.622 - Reward main effect: eta_p^2 = 0.484 - Reward x state interaction: eta_p^2 = 0.679 - Acute stress main effect on stay: eta_p^2 = 0.155 - Cortisol covariate on omega: eta_p^2 = 0.171 - Arousal covariate on omega: eta_p^2 = 0.229
- **learning_from:** Self; own reward outcomes at second stage of sequential decision task (non-social)
- **learning_about:** World; stimulus-reward contingencies and state-transition structure (non-social)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Hybrid MB/MF RL (SARSA(lambda) + MB; 7 params: alpha_1, alpha_2, beta_1, beta_2, lambda, omega, pi)
- **model_family:** MB/MF hybrid
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Full hybrid model (winning)", "family": "Hybrid MB/MF (SARSA(lambda)+MB)", "n_params": 7, "metric": "BIC, BIC_int, XP"},   {"name": "Hybrid, lambda=0", "family": "Hybrid MB/MF (no eligibility trace)", "n_params": 6, "metric": "BIC, BIC_int, XP"},   {"name": "Pure MB (omega=1)", "family": "Model-based only", "n_params": 5, "metric": "BIC, BIC_int, XP"},   {"name": "Pure MF (omega=0)", "family": "Model-free only (SARSA(lambda))", "n_params": 6, "metric": "BIC, BIC_int, XP"},   {"name": "Pure MF, no lambda (omega=0, lambda=0)", "family": "Model-free only (SARSA(0))", "n_params": 5, "metric": "BIC, BIC_int, XP"} ]
- **model_mb_mf:** MB/MF hybrid
- **model_params:** - α_1 (first-stage learning rate): Control M = 0.52 (SD = 0.18), Stress M = 0.47 (SD = 0.17) - α_2 (second-stage learning rate): Control M = 0.49 (SD = 0.18), Stress M = 0.49 (SD = 0.24) - β_1 (first-stage inverse temperature): Control M = 7.89 (SD = 3.07), Stress M = 6.70 (SD = 2.50) - β_2 (second-stage inverse temperature): Control M = 3.80 (SD = 1.26), Stress M = 3.86 (SD = 1.17) - λ (eligibility trace): Control M = 0.55 (SD = 0.13), Stress M = 0.50 (SD = 0.11) - ω (MB/MF weighting): Control M = 0.66 (SD = 0.09), Stress M = 0.66 (SD = 0.09) - π (perseveration): Control M = 0.13 (SD = 0.04), Stress M = 0.13 (SD = 0.04)
- **social_param:** None. No parameters are specifically social; omega indexes MB/MF balance modulated by stress as a contextual factor.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (sum of individual BIC); BIC_int (integrated likelihood approximation); exceedance probability (XP) via random-effects Bayesian model selection (SPM8 spm_BMS)
- **how_model_fit:** individual-level-fit (MAP estimation with Expectation-Maximization; prior = MLE from group)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioural study only)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 39 (all male, ages 21-30, mean = 25.2, SD = 2.73); cortisol responder analyses: n = 32 (7 non-responders excluded for some analyses); heart rate data available for n = 29
- **population_category:** healthy adults
- **population_age_range:** 21–30
- **ecological_validity:** Low to moderate; task is a standard abstract two-step decision task with no social interaction during the task itself. The TSST stress induction is ecologically valid as a potent psychosocial stressor. However, the decision-making task involves abstract stimuli (Chinese characters, colored boxes) with no naturalistic context.
- **eligibility_flag:** The task itself is NOT social -- it is a non-social sequential decision-making task. The stress manipulation (TSST) is social, but the learning that occurs is non-social (learning stimulus-reward contingencies). This paper does NOT meet the criterion "learning occurs in a social context" as the learning itself is about non-social reward contingencies. Flag: "Learning task is non-social; only the stress induction (TSST) is social. No social learning occurs over time.
- **concerns:** - The learning task is entirely non-social -- participants learn abstract stimulus-reward associations. The social element is limited to the stress induction protocol (TSST), not the learning process itself. - Male-only sample limits generalizability. - Cortisol non-responders (n = 7) excluded from some analyses, creating different sample sizes across analyses. - No neuroimaging data collected. - The eligibility trace parameter lambda is referred to with "(cid:2)" in the text extraction (OCR artifact); actual symbol is λ.
- **limitations_reported:** The sample selection criteria of this study might limit the generalizability of our results: only males within an age range of 21-30 years were included"; "further studies are needed to replicate our findings in a broader range of the population.
- **limitations_categorized:** limited generalizability; sample homogeneity (male-only, narrow age range)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - eligibility_flag (HIGH): Task is non-social; only stress induction is social - social_param (HIGH): No social parameters exist in the model - ecological_validity (MEDIUM): Standard lab task with abstract stimuli
- **cannot_find:** - Code/data availability statement - Supplement (no supplement found in papers folder)
- **other_notes:** This paper uses the Daw et al. (2011) two-step task, a cornerstone paradigm for MB/MF arbitration, but the task itself involves no social learning. The only social element is the TSST stress induction protocol. The paper's contribution is showing that individual differences in stress reactivity and chronic stress history moderate the MB/MF balance. This paper may not meet inclusion criteria for a review of computational models of learning in a social context, as the learning process itself is non-social. No supplement file found in papers folder.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- pop_stress
- rr_pop_healthy_adults
- rr_pop_stress
- rr_tax_mod_experiential
- spec_depth = general
- spec_locus = source+target+context
- spec_source = social
- tax_domain_G_uncertainty_volatility
- tax_mod_experiential
- tax_model_MB
- tax_model_MB_MF_hybrid
- tax_model_rescorla_wagner
- tax_param_MB_MF_balance
- tax_param_perseveration
- tax_param_social_weight
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = G_uncertainty_volatility
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_MB_MF_hybrid
- tax_rr_model_family = MB_MF_hybrid
- tax_rr_param_MB_MF_balance
- tax_rr_primary_topic = exploration_exploitation
- tax_rr_topic_exploration_exploitation
- tax_topic_exploration_exploitation
