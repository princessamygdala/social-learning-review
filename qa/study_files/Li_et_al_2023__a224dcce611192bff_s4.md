# Li et al. (2023)

- **study_id:** `a224dcce611192bff_s4`
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
- **study_focus:** Trust learning; social status effect on trustworthiness learning when reciprocity rates are difficult to distinguish (continuous trust game with gradual reciprocity rate changes)
- **study_focus_short:** Trust learning
- **learning_mode_description:** - Learning mode: Learning from partner's reciprocation amount about partner trustworthiness, biased by social status (social value and differential learning rates)   - Learning from:     - Source type (social): other (partner/trustee)     - Source content (social): outcome (reciprocation amount -- continuous)   - Learning about:     - Target type (social): other (partner/trustee)     - Target content (social): state (mental state; trustworthiness)
- **task_description:** Participants played a repeated trust game with continuous investment (0-100 points in increments of 10) with four partners (2 superiors, 2 inferiors). Partners had gradually changing reciprocity rates (median 33%), with trustworthy partners increasing faster and decreasing slower than untrustworthy partners. 224 trials total.
- **task_paradigm:** Trust game
- **players:** Single agent (participant), multi-target (4 partners: SH, SL, IH, IL)
- **n_players:** multi-target (3+)
- **partner_type:** human (recorded)
- **stimuli:** Face photographs from Chicago Face Database, star ratings (3 stars = superior, 1 star = inferior), continuous monetary feedback (reciprocation amounts), point endowment (100 points)
- **method:** behavioural
- **method_full:** behavioural (laboratory)
- **main_result:** - Significant main effects of social status (F(1,57) = 25.514, eta-p-squared = 0.309) and reciprocity rate (F(1,57) = 47.659, eta-p-squared = 0.455) - Significant interaction of status x reciprocity (F(1,57) = 4.581, eta-p-squared = 0.074) - E3b_LR&SV model best fit: outperformed E3b_LR (d = -1.404) and E3b_SV (d = -0.383) - Learning rate for superiors significantly lower than for inferiors (d = -0.401) - Social value parameter theta = 11.126 (SE = 2.978) - Trustworthy inferior and untrustworthy superior received similar trust levels
- **effect_size:** eta-p-squared = 0.309 (social status); eta-p-squared = 0.455 (reciprocity); eta-p-squared = 0.074 (interaction); Cohen's d = -1.404 (LR&SV vs LR); Cohen's d = -0.383 (LR&SV vs SV); Cohen's d = -0.401 (alpha_superior vs alpha_inferior)
- **learning_from:** other (partner); reciprocation amount (continuous)
- **learning_about:** other (partner); trustworthiness (reciprocity rate)  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** E3b_LR&SV: Rescorla-Wagner with social value + status-specific learning rates (alpha_superior, alpha_inferior, theta [S]). Adapted to continuous investment decision.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "E3b_LR", "family": "Rescorla-Wagner with status-specific LRs", "n_params": 2, "metric": "AIC = 1176.551"} - {"name": "E3b_SV", "family": "Rescorla-Wagner + social value", "n_params": 2, "metric": "AIC = 1137.012"} - {"name": "E3b_LR&SV", "family": "Rescorla-Wagner + social value + status-specific LR", "n_params": 3, "metric": "AIC = 1129.787"}
- **model_mb_mf:** MF
- **model_params:** - alpha_superior [S] (learning rate for superior partners): mean = 0.239 (SE = 0.011) - alpha_inferior (learning rate for inferior partners): mean = 0.269 (SE = 0.012) - theta [S] (social value): mean = 11.126 (SE = 2.978)  NOTE: beta is not listed as a separate free parameter in Table 3 for Experiment 3b, unlike Experiments 2 and 3a. The supplement lists free parameters as alpha, beta, theta for all experiments, but Table 3 omits beta. This is flagged.
- **social_param:** theta (social value) -- additional value from social status; alpha_superior [S] -- lower learning rate for superiors indicates less updating from feedback, more consistent trust behavior toward high-status partners
- **social_param_name:** alpha_superior
- **social_param_value:** 0.239
- **social_param_sd:** 0.011
- **social_param_range:** 
- **model_comparison_metric:** AIC; paired t-tests on AIC values
- **how_model_fit:** individual-level-fit (MLE per participant using MATLAB)
- **data_type_fit_to:** choice behavior (continuous: investment amount 0-100)  ### IMPLEMENTATION LEVEL

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
- **sample_size:** N = 58 (31 females; aged 20.48 +/- 2.08 years); laboratory study
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low-moderate -- repeated trust game with fictitious partners; gradually changing reciprocity rates add ecological realism vs fixed rates; continuous investment scale more naturalistic than binary choice
- **eligibility_flag:** 
- **concerns:** No parameter or model recovery; supplement equations not extractable from .txt; beta parameter listed in supplement free parameters but absent from Table 3; the n_params counts in AIC table may not include beta (discrepancy flagged); no posterior predictive checks
- **limitations_reported:** More evidence is needed to support this view"; "learning is a complex process that is not solely motivated by information updating"; "other phases of learning may also be affected by prior knowledge of social statuses, such as information collection and integration
- **limitations_categorized:** limited ecological validity; no parameter recovery; no model recovery; limited generalizability; sample size
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
- **flagged_fields:** beta parameter (MEDIUM -- listed in supplement free parameters but absent from Table 3 results); n_params discrepancy (MEDIUM -- E3b models appear to have fewer listed params than E2/E3a models); supplement equations (LOW -- image-based)
- **cannot_find:** Beta parameter value for E3b models; exact supplement equations; parameter recovery; model simulations
- **other_notes:** This is the only experiment where the combined LR&SV model wins, suggesting that when trustworthiness is harder to detect, both social value AND differential learning rates contribute. The lower learning rate for superiors (alpha = 0.239 vs 0.269, d = -0.401) indicates participants updated beliefs less in response to feedback from high-status partners, treating them more consistently. The social value theta (11.126) is much larger here than in Experiments 2-3a, likely because the investment scale is 0-100 points rather than binary.
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
- tax_param_learning_rate
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
