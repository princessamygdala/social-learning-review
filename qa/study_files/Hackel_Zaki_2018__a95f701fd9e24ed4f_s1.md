# Hackel & Zaki (2018)

- **study_id:** `a95f701fd9e24ed4f_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Hackel, L. M., & Zaki, J. (2018). Propagation of economic inequality through reciprocity and reputation. *Psychological Science, 29*(4), 604–613. https://doi.org/10.1177/0956797617741720
- **citation_short:** Hackel & Zaki (2018)
- **doi:** 10.1177/0956797617741720
- **publication_type:** peer-reviewed journal
- **year:** 2018.0
- **field_of_study:** Psychology
- **affiliations_raw:** Department of Psychology, Stanford University,; Department of Psychology, Stanford University; laboratory, which can indicate; ether to; emails: lhackel@stanford.edu
- **code_url:** 

## Computational level
- **study_focus:** Reciprocity learning; how reward-based reinforcement learning about others' generosity and reward value shapes reciprocity behavior and propagates economic inequality.
- **study_focus_short:** Reciprocity learning
- **learning_mode_description:** - Learning mode: Learning from monetary outcomes shared by givers about givers' generosity and reward value to guide partner choice and reciprocity.   - Learning from:     - Source type (social): other (givers)     - Source content (non-social): outcome (points shared = reward value) and (social): action/policy (proportion shared = generosity)   - Learning about:     - Target type (social): other (givers)     - Target content (social): state (mental state; traits — generosity) and (non-social): outcome (expected reward value)
- **task_description:** Participants ("recipients") repeatedly chose between pairs of givers (represented by face avatars) who had been endowed with high or low wealth and made binary generous/stingy allocations in a modified dictator game. After learning, recipients completed a surprise reciprocity task sharing points back with each giver.
- **task_paradigm:** Dictator game
- **players:** Single agent (participant as recipient), multi-target (4 givers: 2 higher-wealth, 2 lower-wealth)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Face avatars, binary monetary feedback (points shared and total pool available)
- **method:** online / behavioural
- **method_full:** Behavioural (online, MTurk)
- **main_result:** - Main Results:   - Effect of giver generosity on reciprocity (b = 0.09, SE = 0.01, t(65.03) = 9.04, p < .001, 95% CI [0.07, 0.11])   - Effect of giver wealth on reciprocity (b = 0.04, SE = 0.01, t(77.17) = 5.40, p < .001, 95% CI [0.02, 0.05])   - Total variance explained: R²_m = .13, R²_c = .91   - Difference of generosity vs. wealth coefficients (difference = 0.05, SE = 0.01, chi-sq(1) = 22.66, p < .001)   - Correlation between weighting parameter w and preferential reciprocity to higher-wealth givers: r(85) = −.33, p = .002, 95% CI [−0.51, −0.13]
- **effect_size:** - Main Results:   - Effect of giver generosity on reciprocity (b = 0.09, SE = 0.01, t(65.03) = 9.04, p < .001, 95% CI [0.07, 0.11])   - Effect of giver wealth on reciprocity (b = 0.04, SE = 0.01, t(77.17) = 5.40, p < .001, 95% CI [0.02, 0.05])   - Total variance explained: R²_m = .13, R²_c = .91   - Difference of generosity vs. wealth coefficients (difference = 0.05, SE = 0.01, chi-sq(1) = 22.66, p < .001)   - Correlation between weighting parameter w and preferential reciprocity to higher-wealth givers: r(85) = −.33, p = .002, 95% CI [−0.51, −0.13]
- **learning_from:** Other (givers); monetary reward outcomes and generosity proportion
- **learning_about:** Other (givers); generosity (trait) and reward value  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Reward-Generosity Reinforcement Learning model: dual-update RW with weighting parameter (α, w, β). Q_t = Q_{t-1} + α * δ_R; G_t = G_{t-1} + α * δ_G; EV = w * GV + (1-w) * Q; softmax choice.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Reward-Generosity RL model", "family": "Rescorla-Wagner", "n_params": 3, "metric": "MAP estimation"}] - Note: Only one model is reported as tested. The model was validated in prior work (Hackel et al., 2015).
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): single learning rate for both reward and generosity prediction errors. Study 1 mean = 0.32, median = 0.20 - w (weighting parameter) [S]: weight on generosity-based value (w=1) vs. reward-based value (w=0). Study 1 mean = 0.45, median = 0.42 - β (exploration/inverse temperature): controls stochasticity of choice. Study 1 mean = 0.36, median = 0.11
- **social_param:** w (weighting parameter) — indicates the degree to which a participant relies on generosity-based (social, trait-based) versus reward-based (non-social, outcome-based) learning when choosing interaction partners.
- **social_param_name:** w
- **social_param_value:** 0.45
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** N/A — only one model tested; MAP estimation used for parameter fitting
- **how_model_fit:** Individual-level fit (maximum a posteriori estimation with priors: gamma(1.2, scale=5) for β; beta(1.1, 1.1) for α and w)
- **data_type_fit_to:** Choice behavior (learning phase partner selection choices)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Study 1: Wave 1 (givers) N = 100 (50F, 50M; ages 20–66, M = 38.84); Wave 2 (recipients) N = 87 after exclusions (42F, 58M; ages 19–65, M = 35.63; 13 excluded). Replication study: N = 95 after exclusions (from 100 recruited).
- **population_category:** healthy adults
- **population_age_range:** 20–66
- **ecological_validity:** Lab-based online economic game with real monetary stakes (points converted to money). Artificial manipulation of wealth via endowment size creates relative inequality but does not capture real-world wealth dynamics. Use of face avatars and anonymous interaction limits ecological validity. However, real giver decisions (not simulated) enhance validity.
- **eligibility_flag:** 
- **concerns:** Only one computational model tested — no model comparison. The computational model was validated in prior work (Hackel et al., 2015) rather than newly tested here. No parameter recovery or model recovery reported. The weighting parameter w is correlated with reciprocity behavior, but the causal direction is not established. Exclusion of 13% of participants in Study 1 and 15% in Study 2 may bias results.
- **limitations_reported:** Authors note: "Although the influence of wealth was smaller than that of generosity"; "participants gained no advantage here by privileging the wealthy, suggesting that this tendency did not rely on strategic calculation"; the authors acknowledge the effect might be "exacerbated when people do not know a giver's wealth and, therefore, cannot directly infer a giver's proportional generosity.
- **limitations_categorized:** Limited ecological validity; task simplicity; no model comparison; limited generalizability (MTurk sample); no neuroimaging
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
- **wc_rule10:** Yes
- **wc_score:** 4.5
- **wc_total:** 4.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - `all_models_tested`: LOW confidence — only one model described; paper states it was "validated in previous work" but no alternative models compared in this paper   - `model_comparison_metric`: N/A — no model comparison performed (only 1 model)   - `preregistered`: MEDIUM — not mentioned in paper; marked "Not reported"   - `limitations_reported`: MEDIUM — authors discuss limitations in Discussion but do not have a formal limitations section
- **cannot_find:** - No formal model comparison (only 1 model tested)   - No parameter recovery or model recovery   - No simulation studies   - No neuroimaging data   - No explicit preregistration statement
- **other_notes:** The paper also reports 2 pilot studies (N = 46, N = 141) and a replication of Study 1 (N = 95) in the supplement, all showing consistent effects. The computational model is identical across all studies, with only minor adaptations for continuous vs. binary giver allocations in pilot studies. Supplement Table S9 provides fitted parameter values for all studies. Open data and materials available at https://osf.io/aj98f/. The model was originally developed and validated in Hackel, Doll, & Amodio (2015, Nature Neuroscience).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_depth = general
- spec_locus = source+target
- spec_source = social
- spec_target = partly
- tax_domain_B_inference_modelling_others
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_social_weight
- tax_rr_primary_topic = reciprocity
- tax_rr_secondary_topic = reputation_learning
- tax_rr_topic_reciprocity
- tax_rr_topic_reputation_learning
- tax_social_nonsocial_comparison
- tax_topic_reciprocity
- tax_topic_reputation_learning
