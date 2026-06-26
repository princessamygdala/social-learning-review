# Kobza & Bellebaum (2015)

- **study_id:** `acf9caf573646169b_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Kobza, S., & Bellebaum, C. (2015). Processing of action- but not stimulus-related prediction errors differs between active and observational feedback learning. *Neuropsychologia*, *66*, 75–87. https://doi.org/10.1016/j.neuropsychologia.2014.10.036
- **citation_short:** Kobza & Bellebaum (2015)
- **doi:** 10.1016/j.neuropsychologia.2014.10.036
- **publication_type:** peer-reviewed journal
- **year:** 2015.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** InstituteofCognitiveNeuroscience,DepartmentofNeuropsychology,FacultyofPsychology,RuhrUniversityBochum,Universitätsstraße150,; InstituteforExperimentalPsychology,HeinrichHeineUniversityDüsseldorf,Universitätsstraße1,40225Düsseldorf,Germany; ucleus and the striatum (Hoshi towhichexpectationsoffuturerewardvaryoverthecourseof the; ethanpredictedmayserveasa‘teaching Pagnoni et al; lableonline7November2014; mitted (Schultz, 1997,; lableatScienceDirect; etheso-calledreward; emails: christian.bellebaum@hhu.de, stefan.kobza@ruhr-uni-bochum.de
- **code_url:** 

## Computational level
- **study_focus:** Observational learning — comparing neural coding of action-dependent vs. action-independent prediction errors in active vs. observational feedback learning
- **study_focus_short:** Observational learning
- **learning_mode_description:** - Learning mode: Learning stimulus-response-outcome associations from own or observed feedback in a probabilistic card-guessing paradigm   - Learning from:     - Source type (social in observation group; non-social in active group): other (observed agent) / self       - Active group: non-social (self); Observation group: social (other)     - Source content (non-social): outcome (monetary win/loss feedback)   - Learning about:     - Target type (non-social): world (stimulus-response-outcome contingencies)     - Target content (non-social): action/policy (which response to each card maximizes reward)
- **task_description:** Participants saw one of five card cues and guessed whether a hidden number was high or low, receiving +50c or -50c feedback. Active learners chose themselves; observational learners watched the choices and outcomes of a yoked active learner, then both groups were tested with active choices and no feedback.
- **task_paradigm:** Reversal learning
- **players:** Multi-agent (yoked pairs), asymmetric — single agent (participant) learns actively or by observing one other participant's choices and outcomes
- **n_players:** 
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract card symbols (circle, triangle, square, star, hexagon), directional arrows, monetary feedback (+50c / -50c)
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Action-dependent PE activations (striatum, ACC, insula, cerebellum) were stronger in active than observational learners - Action-independent PE activations (putamen, globus pallidus, insula) did not differ between groups - Uncertainty-related cerebellar activations found only in observational learners - Learning performance (test trial accuracy) was comparable between groups (no significant GROUP main effect, F not reported; PROBABILITY x GROUP interaction F[2,58] = 4.346, p = .028, driven by chance-condition response bias)
- **effect_size:** - PROBABILITY main effect on learning accuracy: F[2,30] = 3.682, p = .037 - BLOCK main effect on test accuracy: F[1,29] = 6.452, p = .017 - PROBABILITY main effect on test accuracy: F[2,58] = 8.358, p = .002 - PROBABILITY x GROUP interaction on test: F[2,58] = 4.346, p = .028 - Correlation active learners learning-test block 1: r = .721; block 2: r = .783 - Between-group correlation difference: z = 1.99 (block 1), z = 2.28 (block 2) - VIF for action-independent PE: 3.024 - Note: No Cohen's d, eta-squared, or standardized betas reported; only F-statistics, t-values, Z-scores, and correlation coefficients available
- **learning_from:** Other's (observed) or own actions and monetary outcomes (win/loss feedback to card guesses)
- **learning_about:** World; stimulus-response-outcome associations (which guess for each card cue maximizes reward)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Fictive reinforcement learning model with separate SV and AV updates (δ = 0.2 fixed learning rate weight for SV; individual α per subject/block/cue for AV); action-independent PE = R(t) - V_s(t); action-dependent PE = R(t) - Q_{s,j}(t)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Fictive RL with SV and AV updates (Prevost et al., 2011 adaptation)", "family": "Rescorla-Wagner / delta rule", "n_params": "1 per subject/block/cue (α); δ = 0.2 fixed", "metric": "N/A — single model, parameters calculated from test block performance"}]
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): individually estimated per subject, block, and cue from test block accuracy. No mean fitted value reported. - δ = 0.2 (fixed weight for SV uncertainty-adjusted learning rate) - V_s(t): subjective value of cue s at trial t - Q_{s,j}(t): action value for action j given cue s at trial t [S — in observation condition, reflects observed action values] - U(t): uncertainty (variance of outcome predictions, RL approximation of Kalman filter) - R(t): outcome (+50 or -50 cents)
- **social_param:** No explicitly social parameter. The same model structure is applied to both active and observational learning groups; the "social" aspect is in the between-subjects design (observing another's choices), not a model parameter.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** N/A — only one model used; no formal model comparison
- **how_model_fit:** params-calculated-independently (learning rates derived from test block choice proportions, not fitted via MLE/Bayesian)
- **data_type_fit_to:** choice behavior (test trial accuracy used to derive learning rates; model-derived PEs used as parametric modulators in fMRI GLM)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors — SV, uncertainty, AV difference, action-independent PE, action-dependent PE as parametric modulators in GLM)
- **contrast:** - Action-dependent PE: active > observational learners — right putamen/caudate, medial globus pallidus, ventral ACC, right insula, bilateral cerebellum - Action-independent PE: no significant between-group differences; active learners: left putamen extending to nucleus accumbens, left globus pallidus, right cerebellum, bilateral insula; observational learners: bilateral insula - Uncertainty: observational > active in right middle frontal gyrus; active > observational in right medial frontal gyrus; observational only: bilateral cerebellum declive - AV following response: active only: left putamen - SV of cue: active only: right medial frontal gyrus
- **key_regions:** Action-dependent PE stronger in active learners in putamen, caudate head, medial globus pallidus, ventral ACC, right insula, bilateral cerebellum. Action-independent PE comparable across groups in putamen, globus pallidus, insula. Uncertainty coded in cerebellum (observational only) and middle/medial frontal gyrus.
- **key_regions_abbrev:** caudate, putamen, ACC, insula, AI, cerebellum
- **coordinates_peak:** Action-dependent PE — active learners: - Left putamen: -24, 8, 0 - Left putamen: -16, 12, -6 - Right insula (BA 13): 38, 2, 12 - Right caudate head: 10, 10, -8 - Right putamen: 16, 6, -12 - Right cerebellum declive: 2, -66, -24 - Left cerebellum culmen: -4, -70, -16 - Left inferior frontal gyrus (BA 47): -30, 34, -10 - Right parahippocampal gyrus (BA 36): 34, -34, -16 - Left cerebellum anterior lobe: -20, -44, -30  Action-dependent PE — active > observational: - Right medial globus pallidus: 12, 2, -4 - Right ventral ACC (BA 25): 6, 8, -10 - Right putamen: 16, 6, -12 - Right insula (BA 13): 42, -2, 8 - Right cerebellum declive: 0, -66, -24 - Left cerebellum fastigium: -6, -60, -28 - Right postcentral gyrus (BA 2): 46, -26, 44  Action-independent PE — active learners: - Left putamen: -18, 8, 0 - Left lateral globus pallidus: -26, -16, 4 - Right cerebellum pyramis: 18, -70, -38 - Left inferior frontal gyrus (BA 46): -44, 42, 12 - Right insula (BA 13): 34, -10, 22 - Left insula (BA 13): -38, -8, 16  Action-independent PE — observational learners: - Left insula (BA 13): -38, -20, 12 - Right insula: 40, -16, 2  Uncertainty — observational learners: - Right cerebellum declive: 20, -74, -20 - Left cerebellum declive: -42, -60, -26 - Right middle frontal gyrus (BA 46): 42, 36, 26 - Left middle frontal gyrus (BA 9): -36, 30, 30  Uncertainty — observational > active: - Right middle frontal gyrus (BA 10): 36, 36, 26  Uncertainty — active > observational: - Right medial frontal gyrus (BA 9): 4, 50, 28
- **analysis_type:** whole-brain (Monte Carlo cluster-size corrected, p < .001 voxel, 25 voxel extent) with ROI interpretation framework (predefined bilateral putamen, caudate, globus pallidus, ACC, hippocampus, cerebellum, PFC)  ---  ### QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 31 (16 active learners [6 female; M age = 25.1, SD = 3.7]; 15 observational learners [9 female; M age = 23.9, SD = 4.5]); ages 20-34; 2 excluded for data acquisition problems from original 33
- **population_category:** healthy adults
- **population_age_range:** 20–34
- **ecological_validity:** Low — abstract card-guessing paradigm with monetary outcomes; observation is of pre-recorded choices (not live interaction); between-subjects design limits within-person comparisons
- **eligibility_flag:** 
- **concerns:** - Learning rate α is not fitted via MLE or Bayesian methods but calculated from test block accuracy proportions — this is an unusual approach that limits model comparison - Only one model tested — no formal model comparison - Small sample (N = 16 and 15 per group) for between-subjects fMRI - No parameter recovery or model recovery reported - Fixed δ = 0.2 adopted from Prevost et al. (2011) without justification for this specific task - Cluster correction threshold at p < .01 (not p < .05) with voxel threshold p < .001; 25 voxel extent — relatively liberal - Between-subjects design means groups see different stimuli sequences (yoked but not identical experience)
- **limitations_reported:** EPI not tilted, potentially reducing sensitivity for OFC; no clear picture for medial temporal lobe role; did not find regions more strongly involved in action-dependent PE coding in observational than active learning; learning strategies may differ between groups but not investigated; brain structures beyond reward system supporting observational learning not identified; right-hand bias in active learners for chance condition complicates interpretation
- **limitations_categorized:** limited sensitivity for specific brain regions (no EPI tilt); incomplete characterization of observational learning mechanisms; potential response bias confound; task simplicity; limited ecological validity; sample size
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Partial
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 3.0
- **wc_total:** 3.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_comparison_metric: LOW — no model comparison performed; single model used - social_param: MEDIUM — no explicit social parameter; social dimension is between-subjects manipulation - effect_size: MEDIUM — no standardized effect sizes (Cohen's d, eta-squared) reported; only F-stats, t-values, Z-scores, correlations - how_model_fit: MEDIUM — unusual fitting approach (calculated from test accuracy rather than fitted) - model_params mean fitted values: LOW — individual learning rates not reported as group means
- **cannot_find:** - Mean fitted learning rate (α) values per group - Formal model comparison metrics (only one model) - Standardized effect sizes (d, η², β) - Data/code availability statement - Preregistration information
- **other_notes:** The paper's primary contribution is dissociating action-dependent from action-independent prediction errors in active vs. observational learning. The RL model is used primarily as a tool to generate parametric regressors for fMRI rather than as a test of competing computational accounts. The fictive RL model (Fudenberg & Levine, 1998) updates values for both selected and unselected actions (counterfactual updating). Coordinates reported in MNI space, transformed to Talairach for labelling. All six supplementary tables with full coordinates were accessible.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = shared
- spec_source = partly
- tax_domain_B_inference_modelling_others
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = imitation_emulation
- tax_rr_topic_imitation_emulation
- tax_topic_imitation_emulation
