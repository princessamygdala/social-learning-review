# Allidina (2018)

- **study_id:** `a44cda9eb501547e6_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Allidina, S. (2018). *Stereotype maintenance through approach-contingent information gain* (Master's thesis, University of Toronto). University of Toronto.
- **citation_short:** Allidina (2018)
- **doi:** Not reported (Master's thesis)
- **publication_type:** thesis
- **year:** 2018.0
- **field_of_study:** Psychology
- **affiliations_raw:** ether negative representations are reinforced by avoidance; mitted in conformity with the requirements; Department of Psychology; University of Toronto
- **code_url:** 

## Computational level
- **study_focus:** Stereotype learning / social group learning — how approach-contingent information gain biases learning about social groups, maintaining initially formed stereotypes through avoidance
- **study_focus_short:** Stereotype learning / social group learning
- **learning_mode_description:** - Learning mode: Learning from approach-contingent outcomes about cooperativeness of social group members   - Learning from:     - Source type (social): other (alien group members)     - Source content (non-social): outcome (monetary cooperation/defection feedback)   - Learning about:     - Target type (social): group (alien species categorized by skin colour)     - Target content (social): state (mental state; cooperativeness/disposition)
- **task_description:** Participants view individual aliens from two visually distinct species (characterized by skin colour) and decide to approach or avoid on each trial. If they approach, the alien either gives +$1 (cooperates) or takes -$1 (defects) probabilistically; if they avoid, they receive no feedback. Group composition changes across the task (new members replace old), and cooperation rates shift, testing whether initial group-based beliefs persist.
- **task_paradigm:** Stereotype learning task
- **players:** Single agent (participant), multi-target (two alien groups, 4-8 members per group per phase)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Alien faces (two species distinguished by skin colour — blue vs. green), binary monetary outcomes (+$1 / -$1)
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - Study 1: Group membership influenced approach decisions controlling for real cooperation probability (χ²(1) = 71.21, p < .001); bias generalized to new group members in phase 2 (χ²(1) = 25.78, p < .001)   - Study 2: Partial replication; group effect on approach (χ²(1) = 66.23, p < .001); generalization to new aliens marginal (χ²(1) = 3.57, p = .059) but present in ratings (χ²(1) = 9.06, p = .003)   - Study 3: Group bias in phase 2 approach (χ²(1) = 204.33, p < .001); Extremes Stay condition showed greater bias (interaction χ²(1) = 92.07, p < .001)   - Study 4: Group bias in phase 1 (χ²(1) = 48.14, p < .001); no reliable generalization to new group members with larger group sizes   - Study 5 (gradual change): Strong group-based generalization (χ²(1) = 1490.32, p < .001) persisting to equal-cooperation aliens   - Study 6: Replication of Study 5 (χ²(1) = 1231.61, p < .001); novel third group rated at midpoint   - Study 7: Group bias persisted even when cooperation rates completely reversed; 4-way interaction with trial showed cross-group signaling (χ²(1) = 5.92, p = .015)   - Study 8: Full feedback condition showed more bias than partial feedback in ratings (interaction χ²(1) = 29.43, p < .001), contrary to predictions   - Study 9: Approach-contingent feedback prevented belief updating when bad group became good (4-way interaction χ²(2) = 9.26, p = .010); full feedback → higher approach to changed bad group   - Computational modeling (Study 1): Constant Avoid model with 2 avoidance parameters best fit (AIC = 12167.90, BIC = 12212.46), but model recovery showed overfitting — results interpreted with caution   - No standardized effect sizes (Cohen's d, r, etc.) reported; only chi-square tests from multilevel logistic regression
- **effect_size:** - Main Results:   - Study 1: Group membership influenced approach decisions controlling for real cooperation probability (χ²(1) = 71.21, p < .001); bias generalized to new group members in phase 2 (χ²(1) = 25.78, p < .001)   - Study 2: Partial replication; group effect on approach (χ²(1) = 66.23, p < .001); generalization to new aliens marginal (χ²(1) = 3.57, p = .059) but present in ratings (χ²(1) = 9.06, p = .003)   - Study 3: Group bias in phase 2 approach (χ²(1) = 204.33, p < .001); Extremes Stay condition showed greater bias (interaction χ²(1) = 92.07, p < .001)   - Study 4: Group bias in phase 1 (χ²(1) = 48.14, p < .001); no reliable generalization to new group members with larger group sizes   - Study 5 (gradual change): Strong group-based generalization (χ²(1) = 1490.32, p < .001) persisting to equal-cooperation aliens   - Study 6: Replication of Study 5 (χ²(1) = 1231.61, p < .001); novel third group rated at midpoint   - Study 7: Group bias persisted even when cooperation rates completely reversed; 4-way interaction with trial showed cross-group signaling (χ²(1) = 5.92, p = .015)   - Study 8: Full feedback condition showed more bias than partial feedback in ratings (interaction χ²(1) = 29.43, p < .001), contrary to predictions   - Study 9: Approach-contingent feedback prevented belief updating when bad group became good (4-way interaction χ²(2) = 9.26, p = .010); full feedback → higher approach to changed bad group   - Computational modeling (Study 1): Constant Avoid model with 2 avoidance parameters best fit (AIC = 12167.90, BIC = 12212.46), but model recovery showed overfitting — results interpreted with caution   - No standardized effect sizes (Cohen's d, r, etc.) reported; only chi-square tests from multilevel logistic regression
- **learning_from:** other (alien group members); monetary cooperation/defection outcomes contingent on approach
- **learning_about:** group (alien species); cooperativeness/disposition of group members  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** RW with group-weight + constant avoidance updating (2 avoidance parameters: av_person, av_group; α, β, groupWeight, prior)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Null (no avoidance updating)", "family": "Rescorla-Wagner", "n_params": 4, "metric": "AIC/BIC"},   {"name": "Constant Avoid (1 av)", "family": "Rescorla-Wagner", "n_params": 5, "metric": "AIC/BIC"},   {"name": "Changing Avoid (1 av)", "family": "Rescorla-Wagner", "n_params": 5, "metric": "AIC/BIC"},   {"name": "Constant Avoid (2 avs)", "family": "Rescorla-Wagner", "n_params": 6, "metric": "AIC/BIC"},   {"name": "Changing Avoid (2 avs)", "family": "Rescorla-Wagner", "n_params": 6, "metric": "AIC/BIC"} ]
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): shared for person and group updates; mean fitted value not reported - β (inverse temperature): governs softmax choice; mean fitted value not reported - groupWeight: weight on group value vs. person value in combined value; mean fitted value not reported - prior: initial belief about cooperation probability; mean fitted value not reported - av_person [S]: constant avoidance updating parameter for individual person value; mean fitted value not reported - av_group [S]: constant avoidance updating parameter for group value; mean fitted value not reported
- **social_param:** av_person and av_group — parameters governing how much the value of an individual person and the social group are updated (reinforced negatively) when the participant avoids. groupWeight — degree to which group-level (vs. individual) value drives approach decisions.
- **social_param_name:** av_person
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC, BIC
- **how_model_fit:** individual-level-fit
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Study 1: N=96 (MTurk); Study 2: N=139 (MTurk); Study 3: N=178 (MTurk); Study 4: N=145 (undergraduates); Study 5: N=88 (MTurk); Study 6: N=100 (MTurk); Study 7: N=299 (MTurk); Study 8: N=173 (MTurk); Study 9: N=405 (MTurk). Computational modeling applied to Study 1 data (N=97, 12416 trials).
- **population_category:** undergraduates
- **population_age_range:** 
- **ecological_validity:** Low — uses artificial alien species with coloured skin to minimize social desirability effects; binary monetary outcomes are simplified relative to real social interaction; no face-to-face interaction. Authors acknowledge the artificial environment and note need for more externally valid tasks.
- **eligibility_flag:** This is a Master's thesis with 9 behavioural studies. Computational modeling is applied only to Study 1 data. The modeling results are explicitly flagged by the author as inconclusive due to overfitting (model recovery failed — models with more avoidance parameters were always preferred regardless of generating model). The thesis qualifies as it uses computational modeling with human behavioural data on social learning over time, but the modeling component is preliminary and acknowledged as unreliable. Flag: thesis; modeling results unreliable per author's own assessment.
- **concerns:** - Model recovery failed: simulated data showed that the 2-avoidance-parameter model was preferred even when the null model generated the data, indicating systematic overfitting. Authors explicitly acknowledge this. - No parameter recovery analysis reported. - Mean fitted parameter values not reported for any model. - Only Study 1 was modeled; it is unclear whether findings generalize to other studies in the thesis. - No standardized effect sizes reported (only chi-square statistics from multilevel logistic regression). - The thesis does not report DOI.
- **limitations_reported:** Most studies used participants from Amazon MTurk; generalizability to other samples is uncertain; the task used an artificial environment with alien groups to minimize social desirability effects associated with generalizing based on skin colour; future research should examine the role of avoidance in a more externally valid task; computational modeling results should be interpreted with caution due to issues with overfitting; alternative modeling approaches are needed.
- **limitations_categorized:** limited generalizability; limited ecological validity; task simplicity; overfitting; no parameter recovery; preliminary modeling
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** Partial
- **wc_rule7:** Yes
- **wc_rule8:** No
- **wc_rule9:** Partial
- **wc_rule10:** No
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - effect_size: LOW — no standardized effect sizes (d, r, η²) reported; only χ² from multilevel logistic regression - winning_model: MEDIUM — model was identified as best-fitting but authors explicitly state results should be interpreted with caution due to overfitting - model_params (fitted values): LOW — mean fitted parameter values not reported for any model - doi: LOW — not available (thesis) - wc_3 (simulate): MEDIUM — simulations done post-hoc for recovery, not prior to fitting
- **cannot_find:** - DOI (thesis, likely not assigned) - Mean fitted parameter values for any model - Standardized effect sizes - Supplement not available (thesis — appendices are included in main document)
- **other_notes:** This is a Master's thesis (University of Toronto, 2018) with 9 behavioural studies but computational modeling applied only to Study 1. The author is transparent about the modeling limitations — the model recovery analysis revealed that the preferred model (Constant Avoid, 2 parameters) was selected even when simpler models generated the data, suggesting the model comparison cannot reliably distinguish between the hypotheses tested. The behavioral findings across 9 studies are robust and well-replicated, showing that approach-contingent information gain maintains initial group-based stereotypes, especially when group composition changes gradually. The thesis should be treated as a single extraction unit (one row) since the computational modeling addresses only Study 1 and the behavioral studies all test the same core hypothesis with variations.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_social_info_search
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_D_group_structure_identity
- tax_mod_experiential
- tax_mod_social_info_search
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = D_group_structure_identity
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_D_group_structure_identity
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = stereotype_updating
- tax_rr_secondary_topic = social_info_use
- tax_rr_topic_social_info_use
- tax_rr_topic_stereotype_updating
- tax_topic_social_info_use
- tax_topic_stereotype_updating
