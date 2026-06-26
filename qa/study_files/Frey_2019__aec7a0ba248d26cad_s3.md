# Frey (2019)

- **study_id:** `aec7a0ba248d26cad_s3`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Frey, A.-L. (2019). Social learning in depression: Evidence from computational modelling, neuroimaging, and neurotransmitter depletion (Doctoral thesis, University of Reading). Study 3 (Chapter 4).
- **citation_short:** Frey (2019)
- **doi:** Not available for thesis.
- **publication_type:** thesis
- **year:** 2019.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Centre for Integrative Neuroscience and Neurodynamics; School of Psychology and Clinical Language Sciences; mitters in the learning process by; mitter Involvement in Learning; mitter Functioning and Social; mitted for the degree of; ethora of research has; mitter
- **code_url:** 

## Computational level
- **study_focus:** Neurotransmitter (dopamine and serotonin) involvement in social learning; effects of dietary precursor depletion on behavioral and neural social learning signals
- **study_focus_short:** Neurotransmitter (dopamine and serotonin) involvement in social learning
- **learning_mode_description:** - Learning mode: Learning to predict emotional facial expressions from name cues under neurotransmitter depletion   - Learning from:     - Source type (social): other (faces displaying emotional expressions)     - Source content (social): outcomes (happy/fearful/neutral facial expressions)   - Learning about:     - Target type (social): other (specific individuals identified by name-face pairings)     - Target content (social): state (emotional state; likelihood of displaying happy/fearful expression)
- **task_description:** Healthy volunteers consumed amino acid depletion drinks (5-HT depletion, DA depletion, or placebo) in a double-blind between-subject design, then performed the same social learning task as Study 2 during fMRI: learning name-face-expression contingencies with probabilistic happy, neutral, or fearful outcomes.
- **task_paradigm:** Social conditioning
- **players:** Single agent (participant), multi-target (6 named individuals/faces)
- **n_players:** multi-target (3+)
- **partner_type:** human (recorded)
- **stimuli:** Modified Scandinavian/Eastern European names as cues, facial expressions (happy, neutral, fearful) from Pictures of Facial Affect Series (Ekman & Friesen, 1976), visual analogue rating scales
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - 5-HT depletion impaired social reward learning: lower 75% ratings (p = .010) and higher 25% ratings (p = .002) vs. placebo - 5-HT depleted subjects more uncertain about social reward outcomes vs. placebo (p = .012) - DA depletion showed trend-level increased uncertainty vs. placebo (p = .086) - 5-HT depletion reduced social reward prediction encoding vs. placebo in dACC/dmPFC, premotor/dlPFC, bilateral temporal/fusiform, right insula (all FWE corrected) - DA depletion reduced social reward prediction encoding vs. placebo in pre-SMA/dmPFC and dACC (FWE corrected) - Neural prediction signals reversed in 5-HT depleted group (tracking neutral rather than happy face predictions) - No group differences in striatal ROI PE encoding - No significant differences in RW model parameters between groups
- **effect_size:** - Group x valence x probability interaction: F(3.84, 109.45) = 3.72, p = .008 - 5-HT vs. placebo uncertainty in reward block: F(2,68) = 4.71, p = .012 - Neural effects: all whole-brain FWE cluster-corrected (p values < .05; see coordinate tables) - Depletion efficacy: group x time x amino acid F(2.28, 64.96) = 82.13, p < .001
- **learning_from:** other; emotional facial expressions (happy, fearful, neutral)
- **learning_about:** other; likelihood of specific individuals displaying happy/fearful expressions  ### ALGORITHMIC LEVEL
- **outcome_modality:** face_expression

## Algorithmic level
- **winning_model:** Rescorla-Wagner with learning rate (alpha) and decay (gamma). V(t+1) = V(t) + alpha * [R(t) - V(t)] V(49) = V(49) + gamma * [0.5 - V(49)] where R(t) = 1 for emotional face, 0 for neutral; V initialized at 0.5 Average parameters used for fMRI: social reward alpha = 0.14, gamma = 0.29; social aversion alpha = 0.12, gamma = 0.46
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** Only one model structure reported. [{"name": "RW with decay", "family": "Rescorla-Wagner", "n_params": 2, "metric": "mean squared error"}]
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate) [S]: social reward mean = 0.14, social aversion mean = 0.12 (across all participants). No significant group differences. - gamma (decay): social reward mean = 0.29, social aversion mean = 0.46 (across all participants). No significant group differences.
- **social_param:** alpha (learning rate) [S] -- no significant group differences in this study, but used to generate parametric regressors for fMRI revealing depletion effects on neural social learning signals
- **social_param_name:** alpha
- **social_param_value:** 0.14
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Mean squared error (no formal model comparison across alternative structures)
- **how_model_fit:** individual-level-fit (minimizing mean squared error between model prediction * 100 and likelihood ratings)
- **data_type_fit_to:** self-report ratings (continuous likelihood ratings 0-100%)  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) -- prediction values as parametric modulators at cue onset; outcome and inverse prediction as PE component modulators at face onset. Also univariate GLM for face/cue contrasts.
- **contrast:** - Social reward prediction encoding: Placebo > 5-HT depletion in dACC/dmPFC, premotor/dlPFC, bilateral temporal, right insula, fusiform - Social reward prediction encoding: Placebo > DA depletion in pre-SMA/dmPFC and dACC - Social aversion prediction encoding: 5-HT depletion > Placebo in right thalamus; 5-HT > DA in precentral gyrus - Fearful > neutral faces: Placebo > 5-HT depletion in vmPFC - Social aversion > reward cues: 5-HT > DA in inferior parietal/insula and MCC/dlPFC - Striatal ROI PE: no group differences
- **key_regions:** 5-HT depletion reduced social reward prediction encoding in dACC, dmPFC, dlPFC, bilateral temporal lobe, fusiform gyrus, and right insula. DA depletion reduced prediction encoding in dACC and dmPFC only. Pattern of 5-HT depletion effects closely resembled HD findings in Study 2.
- **key_regions_abbrev:** mPFC, dmPFC, dlPFC, dACC, ACC, insula, FFA
- **coordinates_peak:** Social reward prediction (Placebo > 5-HT Depletion): Premotor (BA 6)/dlPFC (BA 8): -26, 6, 48 Dorsal ACC: 8, 20, 30 Dorsomedial PFC: -8, 48, 34 Left Superior Temporal Lobe: -44, -44, 16 Right Middle Temporal Lobe: 54, -40, 4 Right Lingual/Fusiform Gyrus: 22, -72, -2 Right Insula: 40, -10, -10 Left Fusiform Gyrus: -32, -66, -12  Social reward prediction (Placebo > DA Depletion): Pre-SMA/Dorsomedial PFC: -10, 10, 60 Dorsal ACC: 8, 22, 26  Social aversion prediction (5-HT > Placebo): Right Thalamus: 28, -30, 8  Social aversion prediction (5-HT > DA): Precentral Gyrus: 22, -8, 52  Fearful > Neutral (Placebo): Right dlPFC: 34, 44, 16 Dorsomedial PFC: 10, 42, 26 Pregenual ACC: -2, 28, 12 vmPFC: -16, 46, 14  Fearful > Neutral (Placebo > 5-HT): vmPFC: 18, 42, 14  Aversion > Reward cues (5-HT > DA): Inferior Parietal Lobe: 40, -36, 30 Right Insula: 48, -26, 22 MCC/ACC: -12, 10, 42 dlPFC: 36, 14, 40
- **analysis_type:** both (whole-brain for parametric modulation and face/cue contrasts at voxelwise p < .005 with FWE cluster correction; ROI for striatal PE analysis using 6mm spheres around meta-analysis coordinates: left -10, 8, -6; right 10, 8, -10)  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 70 (24 5-HT depletion, 22 placebo, 24 DA depletion); ages 18-45; 56 females, 14 males; all healthy volunteers
- **population_category:** clinical
- **population_age_range:** 18–45
- **ecological_validity:** Well-controlled double-blind pharmacological manipulation using established dietary depletion protocol with verified plasma amino acid changes. However, healthy (not depressed) sample; acute depletion does not model chronic neurotransmitter deficits in depression; facial expressions of strangers are not highly rewarding stimuli; passive Pavlovian task without interactive social component.
- **eligibility_flag:** FLAG: Healthy volunteer sample only (no depressed participants). The "social agent" is a displayed face (automated system). Still uses computational modeling, human behavioral data, social learning over time. Include but flag that the clinical relevance is indirect (comparison to Study 2 findings).
- **concerns:** - Only one computational model tested (no model comparison) - Depletion may affect multiple neurotransmitter systems (DA depletion also lowers norepinephrine; 5-HT depletion may affect DA via receptor interactions) - Debate about whether precursor depletion truly reduces neurotransmitter release - Scanner upgrade mid-study (controlled for statistically) - Lenient fMRI threshold (p < .005 voxelwise) - No depressed participants -- clinical relevance is indirect - Facial expressions of strangers may not be rewarding enough to elicit robust DA responses - 10 participants excluded as outliers from behavioral analysis - No significant model parameter group differences despite behavioral effects
- **limitations_reported:** Depletion effects on neurotransmitter release are somewhat controversial; DA depletion also affects norepinephrine; 5-HT depletion may interact with DA via receptor subtypes; acute depletion differs from chronic deficits in depression; healthy volunteer sample may differ from clinical depression; stimuli (happy faces of strangers) may not be rewarding enough for robust DA effects; scanner upgrade mid-study; lenient fMRI threshold; single model tested; small sample size; reverse inferences from brain regions
- **limitations_categorized:** pharmacological specificity; limited ecological validity; sample size; subclinical sample; task simplicity; limited model comparison; liberal statistical threshold; reverse inference; confound (scanner upgrade)
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
- pharma_dopamine
- pharma_serotonin
- pop_healthy_adults
- rr_pharma_dopamine
- rr_pharma_serotonin
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_depth = parametric
- spec_locus = target
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_popclass_healthy
- tax_popclass_pharmacological
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = social_approval_reward
- tax_rr_topic_social_approval_reward
- tax_topic_social_approval_reward
