# Arbel et al. (2024)

- **study_id:** `ac490d4a134a2a23a_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Kozakevich Arbel, E., Shamay-Tsoory, S. G., & Hertz, U. (2024). Adaptive empathic response selection is sensitive to multiple dimensions of social interaction. *Communications Psychology*, *2*, 112. https://doi.org/10.1038/s44271-024-00164-8
- **citation_short:** Arbel et al. (2024)
- **doi:** 10.1038/s44271-024-00164-8
- **publication_type:** peer-reviewed journal (registered report)
- **year:** 2024.0
- **field_of_study:** Psychology
- **affiliations_raw:** etheirwell-beingmighttherefore representaninte- useofcontextualcueswhenchoosinganempathicresponseovermultiple; InstituteofInformationProcessingandDecisionMaking(IIPDM),UniversityofHaifa,Haifa,Israel; etheresearchconsensus municatedinternalreactions,butarefrequentlyovertreactionscommu-; ethatthisisanewlearningexperience,triggeredby andrawpixel; DepartmentofPsychology,UniversityofHaifa,Haifa,Israel; ethatchangesin isaprimaryfeatureofempathy5,10; ethatthisisanewlearningexperiencetriggeredby; mpiricalapproachtoinvestigatethe; emails: elen.kozakevich@gmail.com
- **code_url:** https://osf.io/sa9z6/

## Computational level
- **study_focus:** Adaptive empathy — how different dimensions of social distress scenarios (person identity, emotional state, cause of distress) shape empathic response learning and generalization across interactions.
- **study_focus_short:** Adaptive empathy
- **learning_mode_description:** - Learning mode: Learning from feedback about effectiveness of empathic responses to adapt response selection across changing social dimensions   - Learning from:     - Source type (social): other (distressed target person)     - Source content (social): outcome (feedback — whether empathic response relieved target's distress)   - Learning about:     - Target type (social): other (distressed person)     - Target content (social): action/policy (which emotion regulation strategy — reappraisal vs distraction — is effective for this person/emotion/cause)
- **task_description:** Participants received text messages from a simulated friend in distress and chose between two empathic response strategies (reappraisal or distraction), learning through feedback (emoji changing to relieved or remaining distressed) which response was more effective (80% contingency). Across two blocks, one social dimension (person identity, emotional state, or cause of distress) changed between blocks while others remained constant, allowing assessment of dimension-sensitive versus dimension-insensitive learning.
- **task_paradigm:** Empathy / pain task
- **players:** Single agent (participant), single target (simulated friend in distress; 2 instances across blocks)
- **n_players:** single agent (1)
- **partner_type:** none
- **stimuli:** Text-based instant messaging scenarios, avatars, emoji feedback (sad/angry → relieved or unchanged), two emotion regulation strategies (reappraisal text, distraction text)
- **method:** online / behavioural
- **method_full:** Behavioural (online)
- **main_result:** - Dimension-sensitive model fit better than dimension-insensitive model in all three conditions:   - Person condition: BIC_DS = 49.43, BIC_DI = 53.40 (V = 2413, z = 6.33, r = 0.512, 95% CI [0.39, 0.62], p < .001)   - Emotion condition: BIC_DS = 52.77, BIC_DI = 53.81 (V = 4121, z = 2.43, r = 0.201, 95% CI [0.05, 0.35], p = .015)   - Cause condition: BIC_DS = 52.82, BIC_DI = 54.49 (V = 3640, z = 3.48, r = 0.287, 95% CI [0.14, 0.43], p < .001) - Person dimension showed largest effect: dimension sensitivity significantly higher in person (M = 3.97) than cause (M = 1.67; d = 0.32, 95% CI [0.12, 0.54]) and emotion (M = 1.04; d = 0.46, 95% CI [0.29, 0.63]) - Significant three-way interaction (condition × block × trial-number) for person condition (β_std = −0.166, OR = 0.847, 95% CI [0.719, 0.997], p = .046) - Marginal effect of cognitive empathy on dimension sensitivity in emotion condition only (β_std = 0.143, t(143) = 1.729, p = .086, η² = 0.02) - No significant association between cognitive empathy and dimension sensitivity in person or cause conditions
- **effect_size:** r = 0.512 (person), r = 0.201 (emotion), r = 0.287 (cause) for model comparison; d = 0.46 (person vs emotion), d = 0.32 (person vs cause) for dimension sensitivity comparison; Cohen's d = 0.49 (person, t-test), d = 0.27 (emotion, t-test), d = 0.29 (cause, t-test)
- **learning_from:** Other (distressed friend); feedback outcome (emoji indicating whether empathic response relieved distress)
- **learning_about:** Other (distressed person); which empathic response strategy (reappraisal vs distraction) is effective given social context dimensions  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** pain_threat

## Algorithmic level
- **winning_model:** Dimension-sensitive Q-learning (3 params: α, β, p₀; 2 states per dimension instance, 2 actions)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "Dimension-insensitive Q-learning", "family": "Q-learning", "n_params": 3, "metric": "BIC"} 2. {"name": "Dimension-sensitive Q-learning (person)", "family": "Q-learning", "n_params": 3, "metric": "BIC"} 3. {"name": "Dimension-sensitive Q-learning (emotion)", "family": "Q-learning", "n_params": 3, "metric": "BIC"} 4. {"name": "Dimension-sensitive Q-learning (cause)", "family": "Q-learning", "n_params": 3, "metric": "BIC"}  Note: The dimension-sensitive and dimension-insensitive models have the same number of free parameters (3: α, β, p₀) but differ in the number of states (1 state vs 2 states for dimension instances). Each condition used its own dimension-sensitive model compared against the same dimension-insensitive model.
- **model_mb_mf:** MF (model-free)
- **model_params:** - α (learning rate; 0 < α < 1): degree of Q-value updating. Person DS: M = 0.307 ± 0.026; Emotion DS: M = 0.257 ± 0.025; Cause DS: M = 0.324 ± 0.028 - β (inverse temperature; 0 < β < 1 stated but fitted values suggest unbounded): stochasticity of decisions. Person DS: M = 5.955 ± 0.436; Emotion DS: M = 6.663 ± 0.488; Cause DS: M = 6.057 ± 0.463 - p₀ (prior / initial Q-value): initial value for Q(S,A). Person DS: M = 0.335 ± 0.017; Emotion DS: M = 0.428 ± 0.018; Cause DS: M = 0.381 ± 0.019
- **social_param:** The state definition itself is the key social parameter — the dimension-sensitive model creates separate states for different instances of a social dimension (different persons, emotions, or causes), while the insensitive model treats all as one state. No single named social parameter; the social component is in the model structure (state space).
- **social_param_name:** The state definition itself is the key social parameter
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (Bayesian Information Criterion), compared within-subjects using both paired two-tailed t-test and Wilcoxon signed-rank test.
- **how_model_fit:** Individual-level fit (parameters optimised by minimising negative log-likelihood per participant)
- **data_type_fit_to:** Choice behavior (trial-by-trial empathic response selections)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A (no neuroimaging)  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 550 recruited; N = 446 after exclusions (person condition n = 153, emotion condition n = 146, cause condition n = 147); ages ~42 ± 13; approximately equal men/women. Pilot: N = 60 recruited, n = 51 analysed. Online (Prolific, UK and USA).
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Limited — computerised task with predefined responses (participants forced to choose between two fixed strategies rather than generating their own). Mitigated somewhat by use of instant-messaging format and realistic distress scenarios. Authors acknowledge this limitation. Only three dimensions and two response strategies tested. Online study only.
- **eligibility_flag:** 
- **concerns:** - The β parameter is stated to be constrained 0 < β < 1, but fitted values are well above 1 (M values 3–7), suggesting either a typo in the text or the constraint was not actually applied. - The dimension-sensitive and dimension-insensitive models have the same number of free parameters (3), so BIC comparison is equivalent to log-likelihood comparison — the models differ only in state structure, not complexity. This is a valid design choice but means BIC penalisation is identical. - Between-subjects design for condition (person/emotion/cause) means individual differences between groups may confound dimension comparisons. - No neural data collected.
- **limitations_reported:** Capturing learning patterns in a complex setting obliged us to use a simplified experimental version of social interactions"; "the study used a computerised task with predefined responses, and the participants were 'forced' to choose a response instead of typing one"; "this may limit the ecological validity of our results"; "our study was limited to studying only three dimensions, and two empathic response strategies"; "Although we focused on only three dimensions of social interaction, further studies might address other contextual cues
- **limitations_categorized:** Limited ecological validity; task simplicity; limited stimulus/dimension variety; forced-choice design; online-only data collection
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 9.0
- **wc_total:** 9.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - β constraint (MEDIUM): Text states 0 < β < 1 but fitted values are >> 1; likely a typo (should be 0 < β or β > 0) - social_param (MEDIUM): No single named social parameter; the social distinction is in the model structure (state space definition)
- **cannot_find:** Nothing missing — full text and supplement were accessible and extraction is complete.
- **other_notes:** This is a Registered Report published in Communications Psychology (Nature portfolio). The study is purely behavioural with no neuroimaging. The computational modelling is relatively straightforward (two Q-learning variants differing only in state space structure). The paper builds on Kozakevich Arbel et al. (2021) which first demonstrated adaptive empathy learning. The key innovation is extending empathic response learning to a multidimensional paradigm adapted from non-social attention/RL research (Niv et al., 2015).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- spec_depth = parametric
- spec_locus = target
- spec_source = partly
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_active_interaction
- tax_mod_experiential
- tax_model_MF
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_primary_topic = empathy_vicarious
- tax_rr_secondary_topic = prosocial_altruism
- tax_rr_topic_empathy_vicarious
- tax_rr_topic_prosocial_altruism
- tax_topic_empathy_vicarious
- tax_topic_prosocial_altruism
