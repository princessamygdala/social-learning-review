# Li et al. (2023)

- **study_id:** `a224dcce611192bff_s2`
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
- **study_focus:** Trust learning; how social status (hierarchy) biases trustworthiness learning and trust decisions via social value
- **study_focus_short:** Trust learning
- **learning_mode_description:** - Learning mode: Learning from partner's reciprocation feedback about partner trustworthiness, biased by social status (social value)   - Learning from:     - Source type (social): other (partner/trustee)     - Source content (social): outcome (reciprocation: share or keep)   - Learning about:     - Target type (social): other (partner/trustee)     - Target content (social): state (mental state; trustworthiness)
- **task_description:** Participants played a repeated trust game as trustors with three partners (superior, intermediate, inferior status). On each trial, they chose to keep or share 5 yuan; if shared, money was tripled and the partner could reciprocate (50% preprogrammed rate for all partners). 72 trials total (24 per partner).
- **task_paradigm:** Trust game
- **players:** Single agent (participant), multi-target (3 partners: 1 superior, 1 intermediate, 1 inferior)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Face photographs from Chicago Face Database, star ratings (1-3 stars) indicating social status, binary feedback (reciprocate/keep), monetary outcomes
- **method:** behavioural
- **method_full:** behavioural (laboratory)
- **main_result:** - Significant main effect of social status on share rate (F(2,112) = 7.524, eta-p-squared = 0.118) - Superior partners (M = 0.69) trusted more than inferior partners (M = 0.58) - E2_SV model fitted best: outperformed E2_LR (d = -0.928) and E2_LR&SV (d = -1.537) - Social value parameter theta = 1.842 (SE = 0.09)
- **effect_size:** eta-p-squared = 0.118 (social status main effect); Cohen's d = -0.928 (E2_SV vs E2_LR AIC comparison); Cohen's d = -1.537 (E2_SV vs E2_LR&SV AIC comparison)
- **learning_from:** other (partner); reciprocation feedback (share or keep)
- **learning_about:** other (partner); trustworthiness (reciprocity probability)  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** E2_SV: Rescorla-Wagner with social value term (1 alpha, 1 theta [S], 1 beta). P(t+1) = P(t) + alpha * PE(t); PE(t) = gamma(t) - P(t); EV(S)(t) = P(t) * (m * 7.5) + i_socialstatus * theta; IP = softmax(beta * EV)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "E2_LR", "family": "Rescorla-Wagner", "n_params": 4, "metric": "AIC = 80.074"} - {"name": "E2_SV", "family": "Rescorla-Wagner + social value", "n_params": 3, "metric": "AIC = 48.535"} - {"name": "E2_LR&SV", "family": "Rescorla-Wagner + social value + status-specific LR", "n_params": 5, "metric": "AIC = 51.658"}
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate): mean = 0.061 (SE = 0.009) - theta [S] (social value): mean = 1.842 (SE = 0.09) - beta (inverse temperature): mean = 0.931 (SE = 0.024)
- **social_param:** theta (social value) -- represents the additional value assigned to a partner based on their social status, independent of monetary reward. Higher social status = higher social value added to expected value.
- **social_param_name:** theta
- **social_param_value:** 1.842
- **social_param_sd:** 0.09
- **social_param_range:** 
- **model_comparison_metric:** AIC; paired t-tests on AIC values between models
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
- **sample_size:** N = 57 (31 females; aged 20 +/- 1.37 years); laboratory study
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low-moderate -- repeated trust game with fictitious partners; social status manipulated via star labels; deceptive cover story (DIC Project) enhanced believability but partners were preprogrammed
- **eligibility_flag:** 
- **concerns:** Preprogrammed 50% reciprocity rate identical across conditions; participants deceived about partner identity; formulas in supplement extracted as blank image placeholders (cannot verify exact equations from supplement .txt); no parameter recovery or model recovery reported
- **limitations_reported:** More evidence is needed to support this view"; "learning is a complex process that is not solely motivated by information updating"; "other phases of learning may also be affected by prior knowledge of social statuses
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
- **flagged_fields:** model equations from supplement (LOW confidence -- supplement .txt shows blank equation placeholders; main text equations used instead); wc_3 through wc_6 and wc_8 (HIGH confidence -- not described)
- **cannot_find:** Exact supplement equations (image-based, not extractable from .txt); no parameter recovery; no model simulations; no posterior predictive checks
- **other_notes:** The E2_SV model has fewer parameters (3) than the E2_LR model (4) yet fits better, supporting the social value account over differential learning rates. The softmax function for choice probability and Rescorla-Wagner updating rule are standard. The social value parameter theta enters the expected value computation additively, scaled by social status index.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
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
