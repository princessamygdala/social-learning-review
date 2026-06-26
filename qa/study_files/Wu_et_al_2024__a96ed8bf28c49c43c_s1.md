# Wu et al. (2024)

- **study_id:** `a96ed8bf28c49c43c_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Wu, X., Fu, H., Zhang, T., Bao, D., Hu, J., Zhu, R., Feng, C., Gu, R., & Liu, C. (2024). A cognitive computational mechanism for mutual cooperation: The roles of positive expectation and social reward. *Acta Psychologica Sinica*, *56*(9), 1299-1312. https://doi.org/10.3724/SP.J.1041.2024.01299
- **citation_short:** Wu et al. (2024)
- **doi:** 10.3724/SP.J.1041.2024.01299
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Behavioural economics / Economics
- **affiliations_raw:** ethods: Using a repeated version of the Prisoner's Dilemma Game (PDG), we conducted two experiments (n = 134 in Experi-; Center for Neuroeconomics, Department of Economics, University of Zurich, Zurich, 8006, Switzerland); Laboratory of Cognitive Neuroscience and Learning, Beijing Normal University, Beijing 100875, China); Department of Psychology, University of Chinese Academy of Sciences, Beijing 100049, China); Laboratory of Mental Health and Psychological Crisis Intervention, School of Psychology; Laboratory of Behavioral Science, Institute of Psychology, Beijing 100101, China); School of
- **code_url:** 

## Computational level
- **study_focus:** Cooperation learning; conditional cooperation dynamics in repeated Prisoner's Dilemma
- **study_focus_short:** Cooperation learning
- **learning_mode_description:** - Learning mode: Learning from partner's cooperation/defection behavior about partner's cooperation tendency, updating expectations and social reward signals to guide own cooperation decisions   - Learning from:     - Source type (social): other (partner)     - Source content (social): action/policy (cooperation vs. defection choices)   - Learning about:     - Target type (social): other (partner)     - Target content (social): state (mental state; cooperation willingness/expectation)
- **task_description:** Participants played a repeated Prisoner's Dilemma Game with a supposed human partner (social context) and a computer partner (nonsocial context). The partner's cooperation probability was manipulated across blocks (low vs. high), and in Experiment 2, response variability (stable vs. volatile) was additionally controlled.
- **task_paradigm:** Prisoner's dilemma
- **players:** Single agent (participant), dyadic (supposed human partner or computer partner)
- **n_players:** dyadic (2)
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract monetary outcomes (payoff matrix), cooperation/defection choices
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Participants dynamically adjusted cooperation in response to partner's cooperation probability (GLMM: Scenario x Probability interaction, Exp 1) - Partner's cooperation probability increased participant cooperation (Exp 2 GLMM: beta = 0.53, 95% CI [0.12, 0.93]) - Partner's response volatility did not predict cooperation (beta = -0.12, 95% CI [-0.28, 0.05]) - Model 6 (social reward + higher-order belief updating) best explained behavior in both experiments (lowest BIC) - Social reward (omega) was higher in social vs. nonsocial context for high-cooperation partners (Scenario x Probability interaction) - Positive expectation (p) was higher in social vs. nonsocial context for high-cooperation partners (Scenario x Probability interaction) - Scenario x Cooperation rate interaction (Exp 2): beta = -1.08, 95% CI [-1.62, -0.53]
- **effect_size:** - Exp 2 main effect of partner cooperation probability: beta = 0.53, 95% CI [0.12, 0.93] - Exp 2 partner volatility: beta = -0.12, 95% CI [-0.28, 0.05] - Exp 2 Scenario x Cooperation rate: beta = -1.08, 95% CI [-1.62, -0.53]
- **learning_from:** Other (partner); partner's cooperation/defection actions in repeated PDG
- **learning_about:** Other (partner); partner's cooperation willingness/expectation  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Model 6 — Social reward model with higher-order belief updating (parameters: omega [S], p [S], learning rate). Formula not available in English text.
- **model_family:** Bayesian
- **model_class:** PE learning / Belief updating
- **all_models_tested:** 1. {"name": "Model 1 (Baseline Model)", "family": "Random choice", "n_params": "unknown", "metric": "BIC"} 2. {"name": "Model 2 (Reward Learning Model)", "family": "Reward-based RL", "n_params": "unknown", "metric": "BIC"} 3. {"name": "Model 3 (Rational Decision Model)", "family": "Rational choice theory", "n_params": "unknown", "metric": "BIC"} 4. {"name": "Model 4 (Social Reward Model 1)", "family": "RL with social reward", "n_params": "unknown", "metric": "BIC"} 5. {"name": "Model 5 (Social Reward Model 2)", "family": "RL with social reward + integrated learning", "n_params": "unknown", "metric": "BIC"} 6. {"name": "Model 6 (Social Reward Model 3)", "family": "Social reward + higher-order belief updating", "n_params": "unknown", "metric": "BIC"}
- **model_mb_mf:** MF (model-free reward-based learning augmented with belief updating). Confidence: MEDIUM.
- **model_params:** - omega (social reward weight) [S]: additional intrinsic reward from reciprocity. Mean fitted value not reported in English text. - p (positive expectation) [S]: expected willingness of partner to cooperate. Mean fitted value not reported in English text. - Additional parameters (e.g., learning rate) likely present but not specified in available text.
- **social_param:** omega (social reward) — additional intrinsic reward derived from reciprocity; p (positive expectation) — participant's expected willingness of the partner to cooperate
- **social_param_name:** omega
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (Bayesian Information Criterion; BIC = k*ln(n) - 2*ln(L))
- **how_model_fit:** individual-level-fit (inferred from individual-level BIC comparison and individual parameter analysis). Confidence: MEDIUM.
- **data_type_fit_to:** choice behavior (cooperation/defection decisions)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging; authors note future studies might explore neural correlates)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Experiment 1: N = 134 (abstract says 134; figure caption says n = 135). Experiment 2: N = 104. Total across both experiments: ~238.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Limited. Uses a stylized, incentivized Prisoner's Dilemma with programmed (not real) partners; binary choice format constrains the richness of social interaction. Partner responses are algorithmically determined rather than reflecting genuine human interaction. However, the use of monetary incentives and deception about partner identity increases engagement relative to purely hypothetical tasks.
- **eligibility_flag:** 
- **concerns:** - The full article is in Chinese; only an English extended abstract is available. Model formulas, exact parameter counts, and fitted parameter values are not available in the English text. This significantly limits extraction accuracy. - Minor discrepancy in sample size for Exp 1 (n = 134 in abstract vs. n = 135 in figure caption). - Partner is programmed (not a real human), though the social manipulation involves belief about partner identity. - Number of parameters per model is not reported in the English version.
- **limitations_reported:** Authors acknowledge: future studies might explore the neural correlates of these mechanisms; results should be applied to more complex scenarios; there is a gap between laboratory research findings and real-world collaboration.
- **limitations_categorized:** Limited ecological validity; no neuroimaging; task simplicity; limited generalizability (lab-to-real-world gap)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** No
- **wc_score:** 8
- **wc_total:** 8.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_family: MEDIUM — exact formula not available in English text; inferred from description as belief-updating + social reward model - model_mb_mf: MEDIUM — inferred as MF from description - model_params: LOW — only omega and p are named; full parameter list and n_params not available in English text - all_models_tested n_params: LOW — parameter counts not reported in English version - how_model_fit: MEDIUM — inferred from individual BIC comparison - wc_5 (parameter recovery): MEDIUM — may be reported in Chinese text but not in available English summary - sample_size (Exp 1): MEDIUM — discrepancy between 134 and 135
- **cannot_find:** - Exact model formulas for all 6 models (in Chinese text only) - Number of free parameters per model - Fitted parameter values (means, SDs) - Full text of methods, results, and discussion sections (Chinese only) - Whether parameter recovery was performed - Data/code availability statement
- **other_notes:** The original article is published in Chinese in Acta Psychologica Sinica. The English version available is an extended structured abstract with figures but not the full paper. This limits the depth of algorithmic-level extraction. The study uses two experiments with consistent findings, which strengthens confidence in the results. Model recovery analysis (Figure 2b) shows good discriminability among the 6 models. The Exp 1 sample size discrepancy (134 vs. 135) may reflect an exclusion applied after initial enrollment. Both experiments should be treated as a single row since the winning model and theoretical framework are the same across both — Experiment 2 is a conceptual replication with added volatility control.  ---  ## SUMMARY FOR CSV ROW  | Field | Value | |-------|-------| | citation | Wu et al. (2024) | | doi | 10.3724/SP.J.1041.2024.01299 | | publication_type | peer-reviewed journal | | study_focus | Cooperation learning (conditional cooperation) | | learning_source | Other (partner); cooperation/defection actions | | learning_target | Other (partner); cooperation willingness | | source_type | social | | source_content | action/policy | | target_type | social | | target_content | state (mental state) | | winning_model | Social reward + higher-order belief updating (Model 6; omega, p) | | model_family | Belief updating / RL hybrid | | model_class | Prediction error learning / belief updating | | model_mb_mf | MF | | method | behavioural | | analysis_type | N/A | | key_regions | N/A | | sample_size | Exp 1: N=134; Exp 2: N=104 | | preregistered | Not reported | | re_extract_flag | true |
- **re_extract_flag:** true — full text is in Chinese and not accessible for complete extraction. The English extended abstract provides sufficient information for basic extraction but model details (formulas, parameter counts, fitted values) are incomplete.

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_source = social
- spec_target = social
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_bayesian
- tax_model_rescorla_wagner
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_social_bonus
- tax_rr_primary_topic = cooperation
- tax_rr_topic_cooperation
- tax_topic_cooperation
