# Li et al. (2023)

- **study_id:** `a224dcce611192bff_s3`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Li, S., Huang, G., Ma, Z., & Qu, C. (2023). Superior bias in trust-related decisions. *Current Psychology*, *42*, 24822–24836. https://doi.org/10.1007/s12144-022-03567-0
- **citation_short:** Li et al. (2023)
- **doi:** 10.1007/s12144-022-03567-0
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Behavioural economics / Economics
- **affiliations_raw:** Faculty of Education, Northeast Normal University, spectives, their degree of trust in superiors may be related; Laboratory of Mental Health and Cognitive Science, in the daily working life between employees and superiors; Laboratory of Brain, Cognition and Education Sciences, leadership and organizational performance; University, Guangzhou 510631, China (Dahlhaus & Schlösser, 2021); School of Nursing, Peking Union Medical College, No; School of Psychology, Center; emails: zhenlingma@163.com, fondest@163.com
- **code_url:** 

## Computational level
- **study_focus:** Trust learning; social status effect on trustworthiness learning when reciprocity rates are distinguishable (binary trust game with high/low reciprocity rates)
- **study_focus_short:** Trust learning
- **learning_mode_description:** - Learning mode: Learning from partner's reciprocation feedback about partner trustworthiness, biased by social status (social value), with varying trustworthiness levels   - Learning from:     - Source type (social): other (partner/trustee)     - Source content (social): outcome (reciprocation: share or keep)   - Learning about:     - Target type (social): other (partner/trustee)     - Target content (social): state (mental state; trustworthiness)
- **task_description:** Participants played a repeated binary trust game with four partners (2 superiors, 2 inferiors) who had either high (70%) or low (30%) preprogrammed reciprocity rates. On each trial, participants chose to keep or share 5 yuan; 96 trials total (24 per partner).
- **task_paradigm:** Trust game
- **players:** Single agent (participant), multi-target (4 partners: SH, SL, IH, IL)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Face photographs from Chicago Face Database, star ratings (3 stars = superior, 1 star = inferior), binary feedback (reciprocate/keep), monetary outcomes
- **method:** behavioural
- **method_full:** behavioural (laboratory)
- **main_result:** - Significant main effects of social status (F(1,46) = 14.233, eta-p-squared = 0.236) and reciprocity rate (F(1,46) = 46.539, eta-p-squared = 0.503) - Significant main effect of Block (F(7,322) = 5.536, eta-p-squared = 0.107) and Block x reciprocity interaction (F(7,322) = 8.759, eta-p-squared = 0.160) - E3a_SV model best fit: outperformed E3a_LR (d = -1.240) and E3a_LR&SV (d = -0.988) - Social value parameter theta = 2.468 (SE = 0.286)
- **effect_size:** eta-p-squared = 0.236 (social status); eta-p-squared = 0.503 (reciprocity rate); Cohen's d = -1.240 (E3a_SV vs E3a_LR); Cohen's d = -0.988 (E3a_SV vs E3a_LR&SV)
- **learning_from:** other (partner); reciprocation feedback (share or keep)
- **learning_about:** other (partner); trustworthiness (reciprocity probability)  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** E3a_SV: Rescorla-Wagner with social value term (1 alpha, 1 theta [S], 1 beta). Same framework as E2_SV adapted to 2x2 (status x reciprocity) design.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "E3a_LR", "family": "Rescorla-Wagner with status-specific LRs", "n_params": 3, "metric": "AIC = 102.870"} - {"name": "E3a_SV", "family": "Rescorla-Wagner + social value", "n_params": 3, "metric": "AIC = 75.591"} - {"name": "E3a_LR&SV", "family": "Rescorla-Wagner + social value + status-specific LR", "n_params": 4, "metric": "AIC = 76.779"}
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate): mean = 0.127 (SE = 0.016) - theta [S] (social value): mean = 2.468 (SE = 0.286) - beta (inverse temperature): mean = 0.967 (SE = 0.019)
- **social_param:** theta (social value) -- represents additional value assigned to partners based on social status, independent of monetary reward
- **social_param_name:** theta
- **social_param_value:** 2.468
- **social_param_sd:** 0.286
- **social_param_range:** 
- **model_comparison_metric:** AIC; paired t-tests on AIC values
- **how_model_fit:** individual-level-fit (MLE per participant using MATLAB)
- **data_type_fit_to:** choice behavior (binary: share or keep)  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A (no neuroimaging)  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 47 (26 females; aged 20.77 +/- 1.89 years); laboratory study
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low-moderate -- repeated trust game with fictitious partners; preprogrammed reciprocity rates; social status manipulated via star labels
- **eligibility_flag:** 
- **concerns:** Same methodological concerns as Experiment 2; no parameter or model recovery; supplement equations not extractable
- **limitations_reported:** Same as general discussion limitations above
- **limitations_categorized:** limited ecological validity; task simplicity; no parameter recovery; no model recovery; limited generalizability
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
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** supplement equations (LOW -- image-based placeholders)
- **cannot_find:** Exact supplement model equations; parameter recovery; model simulations
- **other_notes:** Theta is larger (2.468) than in Experiment 2 (1.842), suggesting social value effect may be stronger when trustworthiness differences are also present.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = structural
- spec_locus = target
- spec_source = social
- spec_target = social
- tax_domain_C_exchange_interdependence
- tax_domain_D_group_structure_identity
- tax_mod_active_interaction
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_domain_D_group_structure_identity
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_social_bonus
- tax_rr_primary_topic = trust
- tax_rr_secondary_topic = social_hierarchy
- tax_rr_topic_social_hierarchy
- tax_rr_topic_trust
- tax_topic_social_hierarchy
- tax_topic_trust
