# Wittmann et al. (2016)

- **study_id:** `aaa5af466851f84e7_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Wittmann, M. K., Kolling, N., Faber, N. S., Scholl, J., Nelissen, N., & Rushworth, M. F. S. (2016). Self-other mergence in the frontal cortex during cooperation and competition. *Neuron*, *91*(2), 482–493. https://doi.org/10.1016/j.neuron.2016.06.022
- **citation_short:** Wittmann et al. (2016)
- **doi:** 10.1016/j.neuron.2016.06.022
- **publication_type:** peer-reviewed journal
- **year:** 2016.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** CentreforFunctionalMRIoftheBrain,UniversityofOxford,JohnRadcliffeHospital,OX39DUOxford,UK; DepartmentofExperimentalPsychology,UniversityofOxford,SouthParksRoad,OX13UDOxford,UK; DepartmentofPsychiatry,UniversityofOxford,WarnefordHospital,OX37JXOxford,UK; etheirownperformancewiththeperformance MarcoK; ether we estimate our abilities from; ethereisnoclearrightandwrong,; ethertheywillsucceedinagiven; etherwithothers(Misyaketal; emails: marco.wittmann@psy.ox.ac.uk
- **code_url:** 

## Computational level
- **study_focus:** Self-other ability estimation; learning about own and others' abilities in cooperative vs competitive social contexts; self-other mergence (misattribution of performance information between self and other).
- **study_focus_short:** Self-other ability estimation
- **learning_mode_description:** - Learning mode: Learning about one's own and others' abilities from performance feedback in cooperative and competitive contexts   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (own performance feedback on minigame)     - Source type (social): other (relevant other player)       - Source content (social): outcome (other's performance feedback)       - Note: Other's performance also influences self-ability estimates (self-other mergence), and own performance influences other-ability estimates   - Learning about:     - Target type (non-social): self       - Target content (non-social): state (self-ability estimate)     - Target type (social): other (relevant other player)       - Target content (social): state (other-ability estimate)
- **task_description:** Participants performed reaction-time minigames in an MRI scanner while observing predetermined performance feedback for themselves and two confederate players. On each trial, they chose to engage or avoid cooperation/competition with a specified other player, rated expected performance for self and other, played the minigame, and received parametric feedback.
- **task_paradigm:** Social comparison task
- **players:** Single agent (participant), multi-target (2 confederate players; one relevant per trial)
- **n_players:** multi-target (3+)
- **partner_type:** confederate
- **stimuli:** Abstract minigames (time task, color task), numerical performance feedback on 15-point scale, cooperation/competition context cues, variable thresholds
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - Self-other mergence (SOM) in cooperation: O-performance positively predicted S-ability ratings; reversed in competition (SOM_int(O/S), t_23 = 3.39, p = 0.0025)   - Reciprocal SOM: S-performance influenced O-ability ratings in context-dependent manner (SOM_int(S/O), t_23 = 3.21, p = 0.0039)   - S-performance signal in pgACC correlated with behavioral influence of S-performance on S-ability (r = 0.55, p = 0.0053)   - O-performance signal in area 9 predicted SOM_main(O/S) (r = -0.48, p = 0.0177)   - Contextual S-performance signal in area 9 predicted SOM_int(S/O) (r = 0.43, p = 0.0341)   - O-PE signal in area 9 predicted O-influence on S-pChange (r = 0.43, p = 0.0369)   - SOM also affected objective minigame performance adjustments (O-influence on S-pChange, t_23 = 2.25, p = 0.0346)   - Preference for cooperation over competition (t_23 = 3.82, p < 0.01)
- **effect_size:** - Main Results:   - Self-other mergence (SOM) in cooperation: O-performance positively predicted S-ability ratings; reversed in competition (SOM_int(O/S), t_23 = 3.39, p = 0.0025)   - Reciprocal SOM: S-performance influenced O-ability ratings in context-dependent manner (SOM_int(S/O), t_23 = 3.21, p = 0.0039)   - S-performance signal in pgACC correlated with behavioral influence of S-performance on S-ability (r = 0.55, p = 0.0053)   - O-performance signal in area 9 predicted SOM_main(O/S) (r = -0.48, p = 0.0177)   - Contextual S-performance signal in area 9 predicted SOM_int(S/O) (r = 0.43, p = 0.0341)   - O-PE signal in area 9 predicted O-influence on S-pChange (r = 0.43, p = 0.0369)   - SOM also affected objective minigame performance adjustments (O-influence on S-pChange, t_23 = 2.25, p = 0.0346)   - Preference for cooperation over competition (t_23 = 3.82, p < 0.01)
- **learning_from:** Self and other; own and other's performance feedback on minigames
- **learning_about:** Self (own ability estimate) and other (other's ability estimate); abilities are interdependent (self-other mergence)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Rescorla-Wagner reinforcement learning model (1 learning rate alpha per player; updates expected performance based on prediction error between feedback and expected performance). Confidence: MEDIUM -- model details referenced as being in "Supplemental Experimental Procedures 1" which is not accessible.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "RL model (Rescorla-Wagner)", "family": "Rescorla-Wagner", "n_params": "unknown (supplement not accessible)", "metric": "not reported in main text"}]
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate) -- fitted individually per subject; used to compute recency-weighted average of performance feedback (S-performance and O-performance). Exact values not reported in main text (supplement not accessible). - Note: The RL model was used to generate summary statistics of performance histories (S-performance, O-performance) that were then used as regressors in behavioral GLMs and fMRI GLMs. It was not the primary model being tested; rather it served as a tool to summarize performance history.
- **social_param:** No explicitly designated social parameter. The model tracked S-performance and O-performance separately using the same RL update rule. The social component was captured in the behavioral GLM (context x O-performance interaction on S-ability).
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Not reported in main text. The RL model was used as a descriptive tool rather than compared against alternatives.
- **how_model_fit:** individual-level-fit (fitted individually for each subject, per Supplemental Experimental Procedures 1)
- **data_type_fit_to:** choice behavior (performance feedback sequences)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors from RL model used in GLM); whole-brain analysis with subsequent ROI time-course analyses
- **contrast:** - S-performance parametric regressor > baseline: pgACC (0, 40, 6; Z = 3.98), precuneus (-6, -64, 18; Z = 3.38) - O-performance parametric regressor > baseline: area 9 (2, 44, 36; Z = 3.43) - Context-dependent S-performance in area 9 (competition > cooperation interaction) - O-PE signal in area 9 during feedback phase related to S-pChange
- **key_regions:** Self-performance history tracked in pgACC; other-performance history in dorsomedial area 9; area 9 integrated self, other, and contextual information and predicted self-other mergence in both directions; area 9 O-PE during feedback predicted behavioral performance adjustments.
- **key_regions_abbrev:** ACC
- **coordinates_peak:** - Perigenual anterior cingulate cortex (pgACC): 0, 40, 6 - Precuneus: -6, -64, 18 - Brodmann area 9: 2, 44, 36
- **analysis_type:** both (whole-brain family-wise error cluster corrected z > 2.5, p < 0.05; followed by ROI time-course analyses)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 24 (26 recruited, 2 excluded for excessive motion; 9 female; aged 19-31)
- **population_category:** healthy adults
- **population_age_range:** 19–31
- **ecological_validity:** Moderate. Task used abstract minigames with predetermined (false) performance feedback, reducing ecological validity. Confederate players rather than real social interaction. However, cooperation/competition manipulation was behaviorally meaningful and subjects found feedback credible (debriefing questionnaire). Lab-based fMRI study with relatively simple social framing.
- **eligibility_flag:** 
- **concerns:** - Performance feedback was predetermined (not based on actual performance), meaning "learning" was from experimenter-controlled schedules rather than genuine performance - The RL model was used purely as a descriptive summary tool (recency-weighted average), not as a model of the cognitive process per se; the primary analyses were behavioral GLMs - Supplement not accessible -- model details, exact parameter values, and additional figures (S1-S6) could not be verified - Only 24 subjects (2 excluded from 26) - No formal model comparison conducted
- **limitations_reported:** Authors acknowledge that the direction and strength of self-other mergence may depend on the social situation and other constraints; that the effect could be a byproduct of relational computations rather than a primary cognitive mechanism; that predetermined performance feedback was necessary for experimental control but limits naturalistic validity.
- **limitations_categorized:** limited ecological validity; task simplicity; small sample size; no model comparison; limited generalizability
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
- **wc_rule10:** Partial
- **wc_score:** 4.0
- **wc_total:** 4.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM -- exact parameter specifications and fitted values are in Supplemental Experimental Procedures 1 (not accessible) - winning_model: MEDIUM -- full formula is in supplement - model_comparison_metric: LOW -- no model comparison conducted; RL used as descriptive tool - all_models_tested: LOW -- only one model described; cannot verify from supplement - wc_guidelines items 3, 5, 6: MEDIUM -- could be described in supplement
- **cannot_find:** - Exact RL model formula and parameter values (in Supplemental Experimental Procedures 1) - Number of free parameters in RL model - Model comparison details (if any) - Parameter recovery / model recovery results - Details of fMRI acquisition parameters (in Supplemental Experimental Procedures 3) - Figures S1-S6 content
- **other_notes:** - Supplement not accessible (not available as separate file in papers/ folder). The paper heavily references "Supplemental Experimental Procedures" sections 1-3 and Figures S1-S6, Table S1 for critical methodological details including RL model specification, behavioral analysis details, and MRI acquisition parameters. - The RL model in this paper is used as a descriptive/summary tool to create recency-weighted performance estimates, not as a formal computational model of the learning process. The primary analyses use logistic GLMs on behavioral data and parametric regressors in fMRI GLMs. - This paper is primarily about self-other mergence (a systematic bias in ability estimation) rather than a standard computational modeling study. The "computational model" is minimal. - The paper was published in Neuron (2016) and is open access under CC BY license.
- **re_extract_flag:** true (supplement not accessible; model details, fMRI acquisition parameters, and additional analyses are in supplement only)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = target+context
- spec_neural = shared
- spec_source = social
- spec_target = social
- tax_domain_E_self_in_social_context
- tax_mod_action_observation
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = self_belief_confidence
- tax_rr_secondary_topic = self_other_boundary
- tax_rr_topic_self_belief_confidence
- tax_rr_topic_self_other_boundary
- tax_topic_self_belief_confidence
- tax_topic_self_other_boundary
