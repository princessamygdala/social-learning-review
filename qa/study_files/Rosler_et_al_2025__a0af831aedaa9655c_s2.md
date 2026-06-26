# Rosler et al. (2025)

- **study_id:** `a0af831aedaa9655c_s2`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Rosler, I. K., Kerber, I., & Amodio, D. M. (2025). Effects of moral stereotypes on the formation and persistence of group preferences. *Journal of Experimental Social Psychology, 119*, 104750. https://doi.org/10.1016/j.jesp.2025.104750
- **citation_short:** Rosler et al. (2025)
- **doi:** 10.1016/j.jesp.2025.104750
- **publication_type:** peer-reviewed journal
- **year:** 2025.0
- **field_of_study:** Psychology
- **affiliations_raw:** ether moral stereotypes, as compared with stereotypes butes, stereotypes can bias impressions and thus contribute to prejudice; Department of Psychology, University of Amsterdam, Nieuwe Achtergracht 129, REC G, 1001 NK Amsterdam, Netherlands; ether such impressions are more resistant to Although the content and functions of moral stereotypes have been; University of Berlin, Faculty of Life Sciences, Institute of Psychology, Unter den Linden 6, 10099, Berlin; University of Amsterdam, Department of Psychology, PO Box 15900, 1001 NK Amsterdam, The Netherlands; Department of Psychology, Humboldt U
- **code_url:** 

## Computational level
- **study_focus:** Moral stereotype learning; replication of Study 1 with additional test of generalization to novel group members and non-economic social judgments.
- **study_focus_short:** Moral stereotype learning
- **learning_mode_description:** - Learning mode: Learning from reward feedback of stereotyped group members about individual group member reward value, modulated by moral vs. nonmoral group stereotypes, with generalization to novel group members   - Learning from:     - Source type (social): other (group members/players)     - Source content (non-social): outcome (reward feedback: +1 or 0 points)   - Learning about:     - Target type (social): other (individual group members) / group (group-level value representations, including novel members)     - Target content (social): state (mental state; expected reward value / trustworthiness implied by stereotype)
- **task_description:** Identical to Study 1: participants chose between players from two stereotyped groups in a probabilistic reward task. Additionally, participants completed post-task ratings of familiar players (likeability, willingness to work together, hiring likelihood, helping likelihood) and novel group members on the same measures.
- **task_paradigm:** Stereotype learning task
- **players:** Single agent (participant), multi-target (8 players across 2 groups; 4 per group; plus 2 novel group members in post-task)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Avatar images, text-based stereotype descriptions (moral or competence-related), binary reward feedback, post-task Likert rating scales
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - Training phase (first 30 trials): Stereotype Valence x Morality interaction (d = -0.60, z = -3.12, p = .002)   - Moral condition valence effect on initial choices (d = 1.72)   - Nonmoral condition valence effect on initial choices (d = 0.52)   - Test phase: Stereotype Valence x Morality interaction (d = -0.48, z = -2.84, p = .004)   - Test phase moral condition: significant valence effect (d = 0.89)   - Test phase nonmoral condition: no valence effect (d = -0.07, p = .545)   - Post-task ratings of familiar players: Valence x Morality interaction not significant (d = -0.13, p = .474)   - Post-task ratings of novel group members: Valence x Morality interaction significant (d = -0.55, t = -3.01, p = .003)   - Novel members moral condition: significant valence effect (d = 1.53)   - Novel members nonmoral condition: nonsignificant valence effect (d = 0.50, p = .074)   - Test phase group preference predicts novel member preferences (d = 0.54, B = 1.38, p = .004)   - Computational model: Model 4 best fit (Mdn AIC moral = 80.99, nonmoral = 91.25)   - Prior parameter: larger for moral (Mdn = 0.13) vs. nonmoral (Mdn = -0.01) (W = 1227, p = .006)
- **effect_size:** - Main Results:   - Training phase (first 30 trials): Stereotype Valence x Morality interaction (d = -0.60, z = -3.12, p = .002)   - Moral condition valence effect on initial choices (d = 1.72)   - Nonmoral condition valence effect on initial choices (d = 0.52)   - Test phase: Stereotype Valence x Morality interaction (d = -0.48, z = -2.84, p = .004)   - Test phase moral condition: significant valence effect (d = 0.89)   - Test phase nonmoral condition: no valence effect (d = -0.07, p = .545)   - Post-task ratings of familiar players: Valence x Morality interaction not significant (d = -0.13, p = .474)   - Post-task ratings of novel group members: Valence x Morality interaction significant (d = -0.55, t = -3.01, p = .003)   - Novel members moral condition: significant valence effect (d = 1.53)   - Novel members nonmoral condition: nonsignificant valence effect (d = 0.50, p = .074)   - Test phase group preference predicts novel member preferences (d = 0.54, B = 1.38, p = .004)   - Computational model: Model 4 best fit (Mdn AIC moral = 80.99, nonmoral = 91.25)   - Prior parameter: larger for moral (Mdn = 0.13) vs. nonmoral (Mdn = -0.01) (W = 1227, p = .006)
- **learning_from:** Other (group members); reward feedback from chosen player.
- **learning_about:** Other (individual group members) and group (group-level value representations including novel members); reward value / behavioral tendencies of stereotyped group members.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** RW with group-based prior and separate group learning rates (Model 4: αPos, αNeg, P, β; 4 params) — same as Study 1
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** Same 10 models as Study 1 (see above); additionally includes Model 11 in Table S2 (likely the confirmation bias variant with additional parameters, 2 participants excluded for boundary issues)
- **model_mb_mf:** MF
- **model_params:** - αPos [S]: learning rate for positively-stereotyped group (Study 2 moralized Mdn = 0.07, non-moralized Mdn = 0.01) - αNeg [S]: learning rate for negatively-stereotyped group (Study 2 moralized Mdn = 0.07, non-moralized Mdn = 0.05) - P [S]: group-based symmetrical prior (Study 2 moralized Mdn = 0.13, non-moralized Mdn = -0.01) - β: inverse temperature (Study 2 moralized Mdn = 0.19, non-moralized Mdn = 0.14)
- **social_param:** Same as Study 1: P (prior), αPos, αNeg.
- **social_param_name:** αPos
- **social_param_value:** 0.07
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC, BIC
- **how_model_fit:** individual-level-fit (MLE, 50 random starting points per participant)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Study 2: N = 148 recruited, N = 118 after exclusions (Mage = 41.14, SDage = 11.76; 46 females, 65 males, 7 other); US-based, online (CloudResearch)
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Same as Study 1. Limited ecological validity with experimentally created stereotypes and minimal social interactions through avatar-based reward task.
- **eligibility_flag:** 
- **concerns:** Same as Study 1. Additionally: the Stereotype Valence x Morality interaction did not extend to post-task self-report ratings of familiar players — the moral stereotype effect was specific to choice behavior and novel group member ratings. The Study 2 preregistration included an additional hypothesis about negative > positive moral stereotype effects that was not supported and was dropped. Data collection stopped at 148 (not 150 as preregistered) due to an error.
- **limitations_reported:** Same as Study 1 (see above).
- **limitations_categorized:** limited ecological validity; task simplicity; limited generalizability; potential confound (task relevance); stimulus validity
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = target
- spec_source = social
- spec_target = partly
- tax_domain_D_group_structure_identity
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = D_group_structure_identity
- tax_rr_domain_D_group_structure_identity
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = stereotype_updating
- tax_rr_secondary_topic = intergroup_bias
- tax_rr_topic_intergroup_bias
- tax_rr_topic_stereotype_updating
- tax_topic_intergroup_bias
- tax_topic_stereotype_updating
