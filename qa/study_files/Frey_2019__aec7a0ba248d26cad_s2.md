# Frey (2019)

- **study_id:** `aec7a0ba248d26cad_s2`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Frey, A.-L. (2019). Social learning in depression: Evidence from computational modelling, neuroimaging, and neurotransmitter depletion (Doctoral thesis, University of Reading). Study 2 (Chapter 3).
- **citation_short:** Frey (2019)
- **doi:** Not available for thesis; published version likely has a separate DOI.
- **publication_type:** thesis
- **year:** 2019.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Centre for Integrative Neuroscience and Neurodynamics; School of Psychology and Clinical Language Sciences; mitters in the learning process by; mitter Involvement in Learning; mitter Functioning and Social; mitted for the degree of; ethora of research has; mitter
- **code_url:** 

## Computational level
- **study_focus:** Social learning of emotional face predictions; linking neural prediction encoding to real-life social engagement motivation in depression
- **study_focus_short:** Social learning of emotional face predictions
- **learning_mode_description:** - Learning mode: Learning to predict emotional facial expressions from name cues   - Learning from:     - Source type (social): other (faces displaying emotional expressions)     - Source content (social): outcomes (happy/fearful/neutral facial expressions)   - Learning about:     - Target type (social): other (specific individuals identified by name-face pairings)     - Target content (social): state (emotional state; likelihood of displaying happy/fearful expression)
- **task_description:** Participants viewed name cues followed by faces displaying happy, neutral, or fearful expressions with varying probabilities (25%, 50%, 75%). They rated on each trial how likely the named person was to show a particular emotional expression, learning the contingencies over time. Real-life social experience questionnaires were also collected.
- **task_paradigm:** Social conditioning
- **players:** Single agent (participant), multi-target (6 named individuals/faces)
- **n_players:** multi-target (3+)
- **partner_type:** human (recorded)
- **stimuli:** Modified Scandinavian/Eastern European names as cues, facial expressions (happy, neutral, fearful) from Pictures of Facial Affect Series (Ekman & Friesen, 1976), visual analogue rating scales
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - HD showed reduced social learning rates vs. LD in both reward (U = 351, p = .004) and aversion (U = 355, p = .003) blocks - HD ratings closer to 50% across all trial types, indicating increased uncertainty (F(1,41) = 3.67, p = .062) - Task uncertainty x UIS negativity interaction predicted social engagement motivation (beta = -0.32, p = .015; overall R squared = 0.51) - HD showed reduced social reward prediction encoding in superior parietal lobe/precuneus (Z = 3.80, p_FWE = .001) and right insula/supramarginal/STL (Z = 3.47, p_FWE = .045) - Parietal prediction encoding correlated with social engagement motivation (r = .49, p = .002; partial r = .36, p = .027 controlling for BDI and uncertainty) - HD showed increased fearful > neutral face responses in dACC, fusiform, dlPFC, vlPFC, insula, supramarginal, inferior temporal
- **effect_size:** - Learning rate group difference: U = 351, p = .004 (reward); U = 355, p = .003 (aversion) - Regression R squared = 0.51 for social engagement motivation prediction - Parietal prediction - motivation correlation: r = 0.49, p = .002 - Insula prediction - motivation correlation: r = 0.36, p = .023 - Neural group effects all FWE corrected at cluster level
- **learning_from:** other; emotional facial expressions (happy, fearful, neutral)
- **learning_about:** other; likelihood of specific individuals displaying happy/fearful expressions  ### ALGORITHMIC LEVEL
- **outcome_modality:** face_expression

## Algorithmic level
- **winning_model:** Rescorla-Wagner with learning rate (alpha) and decay (gamma). V(t+1) = V(t) + alpha * [r(t) - V(t)] V(49) = V(49) + gamma * [0.5 - V(49)] where r(t) = 1 for emotional face, 0 for neutral; V initialized at 0.5
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** Only one model structure reported (RW with alpha and gamma). No formal model comparison across alternative models. [{"name": "RW with decay", "family": "Rescorla-Wagner", "n_params": 2, "metric": "sum of squared errors"}]
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate) [S]: determines prediction updating speed. Social reward: mean = 0.12 (averaged across all participants). Social aversion: mean = 0.08 (averaged across all). HD significantly lower than LD. - gamma (decay): forgetting between practice and experimental phases. Fitted individually.
- **social_param:** alpha (learning rate) [S] -- significantly lower in HD for both social reward and social aversion blocks
- **social_param_name:** alpha
- **social_param_value:** 0.12
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Sum of squared errors (no formal model comparison across alternative model structures)
- **how_model_fit:** individual-level-fit (minimizing sum of squared errors between model prediction * 100 and likelihood ratings; two-step procedure for handling missing practice data)
- **data_type_fit_to:** self-report ratings (continuous likelihood ratings 0-100%)  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) -- prediction values as parametric modulators at cue onset; outcome and inverse prediction as PE component modulators at face onset. Also univariate GLM for face contrasts.
- **contrast:** - Social reward prediction encoding (parametric modulation by prediction values at cue): LD > HD in parietal and insula - Social aversion prediction encoding: no group differences - Fearful > neutral faces: HD > LD in dACC, fusiform, dlPFC, vlPFC, insula, supramarginal, inferior temporal - Happy > neutral faces: no group differences - Striatal ROI PE components: no group differences
- **key_regions:** Social reward prediction reduced in HD in superior parietal lobe/precuneus and right insula/supramarginal gyrus/superior temporal lobe. HD showed increased responses to fearful vs. neutral faces in dACC, bilateral supramarginal, fusiform, inferior temporal, dlPFC, vlPFC, insula.
- **key_regions_abbrev:** dlPFC, dACC, ACC, insula, precuneus, FFA, parietal
- **coordinates_peak:** Social reward prediction encoding (LD > HD): Superior Parietal Lobe/Precuneus: -18, -58, 68 Right Insula: 48, -20, 18 Right Supramarginal Gyrus: 58, -32, 24 Right Superior Temporal Lobe: 68, -22, 12  Social reward prediction encoding (LD only): Right Inferior Temporal Lobe: 52, -36, -22 Right Superior Temporal Lobe: 44, -24, -4 Right Fusiform Gyrus: 38, -34, -22  Fearful > Neutral faces (HD > LD): Dorsal ACC/MCC: -2, 10, 28 Right Occipital Lobe: 18, -92, -8 Right Fusiform Gyrus: 34, -76, -18 Right dlPFC (BA 8): 50, 24, 42 Right vlPFC (BA 45): 54, 32, 10 Right Insula: 46, 10, 12 Right Supramarginal Gyrus: 36, -46, 50 Right Inferior Temporal Lobe: 58, -54, -4 Left Inferior Temporal Lobe: -54, -58, -14 Left Supramarginal Gyrus: -28, -48, 52
- **analysis_type:** both (whole-brain for parametric modulation and face contrasts; ROI for striatal PE analysis using 6mm spheres around meta-analysis coordinates: left -10, 8, -6; right 10, 8, -10)  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 43 (22 LD, 21 HD); ages 18-45; 31 females, 12 males
- **population_category:** clinical
- **population_age_range:** 18–45
- **ecological_validity:** Facial expression learning is more ecologically valid than abstract stimuli. Included real-life social experience questionnaire linking task to everyday functioning. However, Pavlovian passive observation task (no interactive social component); fear faces as "social aversion" may not fully represent naturalistic social negativity.
- **eligibility_flag:** 
- **concerns:** - Small sample size for fMRI (N=43) - Lenient voxelwise threshold (p < .01 uncorrected, FWE cluster corrected) - Only one model tested (no model comparison) - Fearful faces as social aversion may not be ideal (not unambiguously social) - HD defined by BDI scores, not clinical diagnosis - Practice data missing for 13 participants - Comorbid anxiety not fully controlled
- **limitations_reported:** Small sample size reducing power; HD subjects defined by BDI not clinical diagnosis; anxiety comorbidity; fearful faces may not be ideal social aversion stimulus; lenient fMRI threshold; single model tested (no model comparison); reverse inferences from engaged brain regions; no non-social control condition; missing practice data for some participants
- **limitations_categorized:** sample size; subclinical sample; confound (comorbid anxiety); task simplicity; limited model comparison; liberal statistical threshold; limited ecological validity; reverse inference
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
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - Study 1: doi (LOW -- thesis doi not provided; published version doi not given in thesis text) - Study 1: model_params mean fitted values (MEDIUM -- individual parameter distributions shown in figures but exact mean values not reported in text) - Studies 2 & 3: model comparison (LOW -- only one model structure tested; no alternative models) - Study 3: eligibility_flag (MEDIUM -- healthy volunteers only; social learning from automated face stimuli) - All studies: preregistered (MEDIUM -- not mentioned, assumed No)
- **cannot_find:** - Exact mean fitted parameter values for Studies 1-3 (distributions shown in figures but precise values for each group not tabulated) - DOIs for published versions of Studies 1 and 2 - Any preregistration information
- **other_notes:** - This is a PhD thesis containing 3 studies. Studies 1 and 2 appear to have been published as journal articles: Frey, Frank, & McCabe (2019) and Frey & McCabe (2019). FLAG as potential duplicates if these published versions are also in the paper set. - The thesis provides an exceptionally thorough literature review on social learning, reinforcement learning in depression, and neurotransmitter roles that is highly relevant to the review narrative. - Study 1 used a deceptive paradigm (participants believed feedback came from real people). Study 2 used Pavlovian learning (no choice/action). Study 3 was pharmacological in healthy volunteers. - The integration across three studies (behavioral, neural, pharmacological) provides a rare multi-level investigation of social learning. - The computational modeling is relatively basic in Studies 2 and 3 (single RW model, no model comparison), which is a notable limitation compared to Study 1's comprehensive 24-model comparison. - Key finding across studies: social reward prediction encoding was reversed (tracking neutral faces rather than happy faces) in both HD individuals and 5-HT depleted healthy volunteers, suggesting a serotonergic mechanism for social learning deficits in depression.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_depression
- pop_healthy_adults
- rr_pop_depression
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_depth = parametric
- spec_locus = target
- spec_neural = shared
- spec_source = social
- spec_target = social
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = social_approval_reward
- tax_rr_topic_social_approval_reward
- tax_topic_social_approval_reward
