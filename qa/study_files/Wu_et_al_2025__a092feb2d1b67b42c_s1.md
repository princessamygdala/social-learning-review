# Wu et al. (2025)

- **study_id:** `a092feb2d1b67b42c_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Wu, X., Fu, H., Aydogan, G., Feng, C., Qin, S., Zeng, Y., & Liu, C. (2025). The self-interest of adolescents overrules cooperation in social dilemmas. *bioRxiv*. https://doi.org/10.1101/2020.10.26.354704
- **citation_short:** Wu et al. (2025)
- **doi:** 10.1101/2020.10.26.354704
- **publication_type:** preprint
- **year:** 2025.0
- **field_of_study:** Psychology
- **affiliations_raw:** 
- **code_url:** 

## Computational level
- **study_focus:** Cooperation learning; developmental differences in reciprocity valuation between adolescents and adults during repeated social dilemmas
- **study_focus_short:** Cooperation learning
- **learning_mode_description:** - Learning mode: Learning from partner's cooperative/defection choices about partner's cooperation probability and updating intrinsic reward for reciprocity   - Learning from:     - Source type (social): other (anonymous partner)     - Source content (social): action/policy (cooperation vs. defection decisions)   - Learning about:     - Target type (social): other (anonymous partner)     - Target content (social): state (mental state; cooperation probability / trustworthiness)       - Also: outcome (intrinsic reward for reciprocity, p x ω) [joint — depends on both partner's cooperation and own social preference]
- **task_description:** Participants played a 120-trial repeated Prisoner's Dilemma Game with a computer-simulated partner whose cooperation probability was pre-programmed (78% stable, then alternating 20%/80%/20% blocks, counterbalanced). Each trial, both players simultaneously chose cooperate or defect, with payoffs of 4/4 (mutual cooperation), 2/2 (mutual defection), 0/6 (cooperate/defect), or 6/0 (defect/cooperate).
- **task_paradigm:** Prisoner's dilemma
- **players:** Single agent (participant), dyadic (anonymous partner, computer-simulated)
- **n_players:** dyadic (2)
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract symbols (triangle = cooperation, square = defection), monetary token outcomes, 10-point cooperativeness rating scale
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Adolescents cooperated less than adults overall (b = 0.79, 95% CI [0.311, 1.270], p = .001)   - Group x previous trial x partner's choice interaction on cooperation (b = 0.24, 95% CI [0.126, 0.361], p < .001)   - Adolescents cooperated less than adults after partner cooperation (t(259) = -2.84, p = .005, BF10 = 6.01) but not after partner defection (t(259) = -1.86, p = .064, BF10 = 0.69)   - Adolescents had higher positive learning rate α+ (t(259) = 2.95, p = .003, BF10 = 8.02)   - Adolescents had lower negative learning rate α− (t(259) = -2.62, p = .009, BF10 = 3.46)   - Adolescents had weaker social preference ω (t(259) = -3.03, p = .003, BF10 = 9.92)   - Adolescents had higher inverse temperature β (t(259) = 2.14, p = .034, BF10 = 1.17)   - Age correlated with α− (r = 0.21, p < .001), ω (r = 0.20, p < .001), and β (r = -0.17, p = .007)   - No group difference in partner cooperation expectations (b = -0.04, 95% CI [-0.102, 0.021], p = .198)   - Group difference in intrinsic reward for reciprocity (b = 0.52, 95% CI [0.224, 0.816], p < .001)
- **effect_size:** - Main Results:   - Adolescents cooperated less than adults overall (b = 0.79, 95% CI [0.311, 1.270], p = .001)   - Group x previous trial x partner's choice interaction on cooperation (b = 0.24, 95% CI [0.126, 0.361], p < .001)   - Adolescents cooperated less than adults after partner cooperation (t(259) = -2.84, p = .005, BF10 = 6.01) but not after partner defection (t(259) = -1.86, p = .064, BF10 = 0.69)   - Adolescents had higher positive learning rate α+ (t(259) = 2.95, p = .003, BF10 = 8.02)   - Adolescents had lower negative learning rate α− (t(259) = -2.62, p = .009, BF10 = 3.46)   - Adolescents had weaker social preference ω (t(259) = -3.03, p = .003, BF10 = 9.92)   - Adolescents had higher inverse temperature β (t(259) = 2.14, p = .034, BF10 = 1.17)   - Age correlated with α− (r = 0.21, p < .001), ω (r = 0.20, p < .001), and β (r = -0.17, p = .007)   - No group difference in partner cooperation expectations (b = -0.04, 95% CI [-0.102, 0.021], p = .198)   - Group difference in intrinsic reward for reciprocity (b = 0.52, 95% CI [0.224, 0.816], p < .001)
- **learning_from:** Other (partner); partner's cooperation/defection choices trial-by-trial
- **learning_about:** Other (partner); partner's cooperation probability (expectations) and intrinsic reward for reciprocity  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Social reward model with asymmetric RL rule (Model 8): p_{t+1} = p_t + α+ δ(PE) + α− (1−δ) PE, where PE = P_t − p_t; U_coop = p_t(4 + ω); U_def = 4p_t + 2; softmax with β. (4 free parameters: α+, α−, ω, β)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Baseline (Bernoulli)", "family": "null/random", "n_params": 1, "metric": "AICc + PEP"},   {"name": "Win-stay & loss-shift", "family": "heuristic", "n_params": 1, "metric": "AICc + PEP"},   {"name": "Reward learning (RL)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "AICc + PEP"},   {"name": "Inequality aversion", "family": "utility function", "n_params": 3, "metric": "AICc + PEP"},   {"name": "Social reward (no learning)", "family": "utility function", "n_params": 3, "metric": "AICc + PEP"},   {"name": "Social reward + RL", "family": "Rescorla-Wagner + utility", "n_params": 3, "metric": "AICc + PEP"},   {"name": "Social reward + influence learning", "family": "Rescorla-Wagner + influence", "n_params": 4, "metric": "AICc + PEP"},   {"name": "Social reward + asymmetric RL (WINNING)", "family": "Rescorla-Wagner (asymmetric)", "n_params": 4, "metric": "AICc + PEP"},   {"name": "Social reward + Pearce-Hall learning", "family": "Pearce-Hall", "n_params": 4, "metric": "AICc + PEP"} ]
- **model_mb_mf:** MF
- **model_params:** - α+ (positive learning rate): learning rate for better-than-expected prediction errors; adolescents > adults (t(259) = 2.95, p = .003) [S — applied to social partner's cooperation feedback] - α− (negative learning rate): learning rate for worse-than-expected prediction errors; adolescents < adults (t(259) = -2.62, p = .009) [S — applied to social partner's defection feedback] - ω (social reward weight): non-monetary bonus for mutual cooperation; adolescents < adults (t(259) = -3.03, p = .003) [S — intrinsic social reward for reciprocity] - β (inverse temperature): sensitivity to utility differences; adolescents > adults (t(259) = 2.14, p = .034)
- **social_param:** ω — social reward weight representing an additional non-monetary reward for mutual cooperation (reciprocity bonus). The term p × ω quantifies the intrinsic reward for reciprocity. Adolescents showed significantly lower ω than adults.
- **social_param_name:** ω
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AICc (corrected Akaike Information Criterion) + Protected Exceedance Probability (PEP) from group-level Bayesian model selection
- **how_model_fit:** individual-level-fit (MLE with fmincon, 500 random starting points per participant; supplementary hierarchical Bayesian estimation via RStan with 4 chains x 4000 iterations)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A — no neuroimaging data collected
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 261 (127 adolescents, aged 14-17, M = 16.13, SD = 0.63, 44 females; 134 adults, aged 18-30, M = 21.63, SD = 2.88, 79 females)
- **population_category:** mixed
- **population_age_range:** 14–17
- **ecological_validity:** Low-moderate. Computer-simulated partner with pre-programmed cooperation probabilities rather than real human interaction. Abstract symbols (triangle/square) rather than naturalistic social cues. Lab setting. PDG payoff structure may bias toward defection beyond intrinsic preferences.
- **eligibility_flag:** 
- **concerns:** No a priori power analysis conducted. Computer-simulated partner rather than real human partner limits ecological validity. 18-year boundary between adolescence/adulthood is arbitrary. Adolescent and adult groups differ in demographic characteristics beyond age (socioeconomic status, financial independence). Gender imbalance between groups (44/127 = 35% female adolescents vs. 79/134 = 59% female adults). PDG payoff structure structurally incentivizes defection, which may confound interpretation of cooperation preferences.
- **limitations_reported:** We used artificial opponents with pre-determined cooperation patterns to better control the stimuli"; "it's possible that participants might behave differently in more natural settings"; "the rPDG may influence choices beyond participants' intrinsic preferences" due to its zero-sum framework that structurally incentivizes defection; "adolescents and adults may still differ in socioeconomic status, financial independence, and social experience"; "this interpretation remains tentative and requires further validation in future research
- **limitations_categorized:** limited ecological validity; artificial opponent (no real social interaction); task structure may confound results; potential demographic confounds; limited generalizability
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 10
- **wc_total:** 10.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - effect_size: MEDIUM — multiple Bayes factors and t-statistics reported but no standardized effect sizes (Cohen's d, η²) for main group comparisons - model_params fitted values: MEDIUM — group-level mean fitted parameter values not numerically reported in text; only group comparison statistics and posterior density plots (Figure 2—figure Supplement 5) provided
- **cannot_find:** - Exact mean fitted parameter values for α+, α−, ω, β per group (only comparison statistics reported; distributions shown in Figure 2—figure Supplement 2 but numerical means not stated in text) - Standardized effect sizes (Cohen's d) for key comparisons
- **other_notes:** This is a bioRxiv preprint (version posted December 23, 2025). The title in the filename ("The selfish nature in interpersonal exchange among adolescents") differs from the actual title in the paper ("The self-interest of adolescents overrules cooperation in social dilemmas"). No supplement file found separately — the paper includes appendix analyses, tables, and figure supplements inline. The hierarchical Bayesian estimation (Stan/RStan) was used as a supplementary validation of the MLE results. Model 9 (Pearce-Hall) was tested in appendix and did not outperform Model 8.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_healthy_adults
- rr_pop_adolescents
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_C_exchange_interdependence
- tax_mod_active_interaction
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_social_bonus
- tax_param_social_weight
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_social_weight
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = cooperation
- tax_rr_secondary_topic = reciprocity
- tax_rr_topic_cooperation
- tax_rr_topic_reciprocity
- tax_topic_cooperation
- tax_topic_reciprocity
