# Bray & Doherty (2007)

- **study_id:** `abbaa5732e78c069d_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Bray, S., & O'Doherty, J. (2007). Neural coding of reward-prediction error signals during classical conditioning with attractive faces. *Journal of Neurophysiology*, 97(4), 3036–3045. https://doi.org/10.1152/jn.01211.2006
- **citation_short:** Bray & Doherty (2007)
- **doi:** 10.1152/jn.01211.2006
- **publication_type:** peer-reviewed journal
- **year:** 2007.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** ether a reward prediction error signal is engaged during learning; ucleus accumbens during presentation of attractive faces; ether behavioral preferences for these stimuli could be; Division of Humanities and Social Sciences; ether it was possible to establish; Institute of Technology; mith and Engel 1968); emails: jdoherty@hss.caltech.edu
- **code_url:** 

## Computational level
- **study_focus:** Classical conditioning with attractive faces; learning conditioned value of neutral stimuli paired with socially rewarding faces (facial attractiveness as visual reward)
- **study_focus_short:** Classical conditioning with attractive faces
- **learning_mode_description:** - Learning mode: Learning from face presentation/omission outcomes about the reward-predictive value of neutral visual cues (fractals)   - Learning from:     - Source type (social): other (face stimuli — attractive/unattractive faces)     - Source content (social): outcome (face presentation or omission as reward/non-reward)   - Learning about:     - Target type (non-social): world (fractal cue–face associations; conditioned value of arbitrary stimuli)     - Target content (non-social): stimulus (reward-predictive value of fractal cues)
- **task_description:** Participants viewed abstract fractal images (CS) that were paired with attractive or unattractive male and female faces (UCS) in a classical conditioning paradigm, with 50% reinforcement after an initial fully-reinforced period. They indicated which side of the screen the fractal appeared on via button press; pleasantness ratings and preference rankings for fractals were collected pre- and post-conditioning.
- **task_paradigm:** Social conditioning
- **players:** Single agent (participant), no interactive partners (faces are static stimuli)
- **n_players:** single agent (1)
- **partner_type:** none
- **stimuli:** Abstract fractal images (CS), photographs of attractive and unattractive male and female faces (UCS), pleasantness rating scale (-10 to +10), preference ranking via pairwise comparisons
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Pleasantness ratings for fractals paired with attractive female faces increased significantly post-conditioning (Z = 2.169, N = 28) - Male subjects showed significantly greater preference increase for fractals paired with attractive vs. unattractive female faces (Z = 2.428, N = 13) - RW model fit to reaction times: Attractive female α = 0.026 (R² = 0.59), Attractive male α = 0.04 (R² = 0.43), Unattractive female α = 0.038 (R² = 0.48), Unattractive male α = 0.04 (R² = 0.57) - Prediction error for attractive > unattractive faces: bilateral NAcc (left: Z = 3.38; right: Z = 3.12) - Opposite-sex attractive > unattractive: left NAcc (Z = 3.52), bilateral medial OFC (left Z = 3.63; right Z = 3.22), right caudate (Z = 3.37) - Amygdala showed positive PE correlations for both attractive and unattractive faces
- **effect_size:** - RW fit to RT: R² = 0.59 (attractive female), R² = 0.43 (attractive male), R² = 0.48 (unattractive female), R² = 0.57 (unattractive male) - NAcc PE contrast (attractive vs. unattractive, opposite sex, heterosexual males): t = 3.01, dof = 8 - NAcc PE contrast (attractive vs. unattractive, opposite sex, heterosexual females): t = 3.16, dof = 12 - NAcc PE contrast (opposite sex, pooled): t = 4.31, dof = 21
- **learning_from:** Other (attractive/unattractive faces as social reward outcomes); source: social stimuli (faces)
- **learning_about:** World; conditioned reward-predictive value of neutral fractal cues  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** Rescorla-Wagner (1 α per condition, derived from RT; δ = R − V; V = V + αδ). Also tested TD extension for ROI analysis.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Rescorla-Wagner", "family": "Rescorla-Wagner", "n_params": 1, "metric": "R² fit to group-averaged RT"}]
- **model_mb_mf:** MF
- **model_params:** - α (learning rate) — derived per trial type from RT regression: α = 0.026 (attractive female), α = 0.04 (attractive male), α = 0.038 (unattractive female), α = 0.04 (unattractive male) - R (outcome value): R = 1 (face presented), R = 0 (face omitted) - δ (prediction error): δ = R − V - V (expected value): updated trial-by-trial
- **social_param:** None explicitly designated as social. The social content is in the UCS (faces) rather than in a dedicated model parameter.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** R² (regression of model-derived learning signal against group-averaged reaction times)
- **how_model_fit:** params-calculated-independently (learning rates derived from group-averaged RT data via regression over a range of α values, then applied to fMRI)
- **data_type_fit_to:** response times (behavioral) and neural activity (fMRI parametric regressors)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — prediction error signal from RW model entered as parametric regressor in GLM
- **contrast:** - PE attractive > PE unattractive (NAcc bilateral) - PE opposite-sex attractive > PE opposite-sex unattractive (NAcc, mOFC, caudate) - PE attractive faces alone (positive correlation; right NAcc) - PE unattractive faces alone (negative correlation; left NAcc) - PE attractive faces (amygdala, positive correlation) - PE unattractive faces (amygdala, positive correlation) - Main effect attractive > unattractive faces (mOFC, NAcc, cingulate)
- **key_regions:** Reward prediction error in bilateral nucleus accumbens for attractive > unattractive faces; opposite-sex PE effect in medial OFC and caudate; amygdala PE for both attractive and unattractive faces; main effect of attractiveness in medial OFC/mPFC.
- **key_regions_abbrev:** NAcc, caudate, mPFC, OFC, ACC, AI, amygdala
- **coordinates_peak:** Table 1 — Prediction error contrasts: - Right inferior frontal gyrus: 39, 30, 18 (Z = 3.74) [Attr > Unattr] - Left inferior frontal gyrus: -36, 33, 15 (Z = 3.70) [Attr > Unattr] - Left nucleus accumbens: -9, 15, -3 (Z = 3.38) [Attr > Unattr] - Right inferior frontal gyrus: 36, 30, 18 (Z = 3.79) [Opp-sex Attr > Unattr] - Left inferior frontal gyrus: -39, 30, 18 (Z = 3.38) [Opp-sex Attr > Unattr] - Left nucleus accumbens: -9, 15, -6 (Z = 3.52) [Opp-sex Attr > Unattr] - Left medial OFC: -6, 33, -9 (Z = 3.63) [Opp-sex Attr > Unattr] - Right medial OFC: 9, 33, -12 (Z = 3.22) [Opp-sex Attr > Unattr] - Right caudate: 9, 15, 6 (Z = 3.37) [Opp-sex Attr > Unattr] Additional from text: - Right NAcc (PE attractive alone): 6, 15, -12 - Left NAcc (PE unattractive alone): -6, 12, -3 - Right amygdala (PE attractive): 24, 0, -25 (Z = 3.31) - Right amygdala (PE unattractive): 18, -6, -21 (Z = 4.02) - Left amygdala (PE unattractive): -18, -6, -18 (Z = 3.26) Table 2 — Main effect of attractiveness: - Right inferior frontal gyrus: 39, 24, 18 (Z = 3.70) - Left inferior frontal gyrus: -39, 36, 15 (Z = 4.70) - Left nucleus accumbens: -9, 15, -6 (Z = 4.28) - Medial anterior cingulate: 0, 36, 12 (Z = 3.76) - Medial posterior cingulate: -3, -30, 30 (Z = 4.51) - Medial OFC (main effect): 12, 39, -9 (Z = 2.93)
- **analysis_type:** ROI (a priori ROIs: striatum, OFC, amygdala; small volume correction applied)  ---  ### QUALITY
- **analysis_type_clean:** ROI
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 28 (15 female, 13 male; ages 18–27, mean 20.8 ± 2.24); N = 25 for imaging analysis (3 excluded for technical issues); N = 27 for RT analysis; N = 27 for preference data
- **population_category:** healthy adults
- **population_age_range:** 18–27
- **ecological_validity:** Low ecological validity — static face photographs as UCS in a Pavlovian paradigm; no real social interaction; faces masked to remove hair; lab-based fMRI study with button-press responses only.
- **eligibility_flag:** Borderline — the "social" element is limited to attractive faces serving as reward stimuli. There is no social interaction, no social agent producing outcomes, and no learning about another person's mental states or behavior. The faces function as visual reinforcers (like juice or money) rather than as social agents. The learning is classical conditioning of cue-reward associations, not social learning per se. FLAG: borderline social context; faces as reward stimuli rather than social agents.
- **concerns:** - Only one model tested (RW); no formal model comparison - Learning rate derived from group-averaged RT, not individual-level fitting - No parameter recovery or model recovery - Social content is debatable — faces function as reward stimuli analogous to juice/money, not as social agents - Small volume correction used throughout; no whole-brain corrected results reported - 50% reinforcement schedule after initial 100% may confound early vs. late learning - No explicit awareness measure included in the model
- **limitations_reported:** Authors acknowledge: the study does not distinguish between primary and secondary reinforcer accounts of striatal function; the nature of unconditioned responses to different reinforcer types needs further investigation; the behavioral effect was primarily observed for attractive female faces and in male subjects, limiting generalizability; the longer UCS duration (1.5s) compared to prior conditioning studies may affect comparability.
- **limitations_categorized:** limited generalizability; task simplicity; limited ecological validity; no model comparison; group-level parameter estimation
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Partial
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** No
- **wc_score:** 3.0
- **wc_total:** 3.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `eligibility_flag`: MEDIUM — the paper uses faces as reward stimuli but the social context is borderline; faces function more as visual reinforcers than social agents - `learning_mode target_type`: MEDIUM — coded as "world" (conditioned value of cues) but could arguably be "stimulus" under a different interpretation - `social_param`: HIGH — no explicitly social parameter exists in the model - `model_comparison_metric`: MEDIUM — R² used descriptively for RT fit, not as formal model comparison - `how_model_fit`: MEDIUM — described as regression over range of α values on group-averaged data; coded as "params-calculated-independently
- **cannot_find:** - No supplement available to check for additional model details or coordinates - No formal effect sizes (Cohen's d, η²) reported for behavioral conditioning effects — only Z-scores and t-values provided - No individual-level model fitting details
- **other_notes:** This is an early (2007) model-based fMRI study applying RW prediction errors to social reward (faces). The paper's contribution is showing that attractive faces engage the same PE signals as other rewards (juice, money) in ventral striatum. The "social" aspect is limited — the paper itself frames faces as visual rewards rather than social agents. The TD learning extension is used only in a follow-up ROI analysis, not as the main model. No supplement was found. The paper predates Wilson & Collins (2019) guidelines by over a decade, which explains the low WC scores.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = general
- spec_locus = source
- spec_neural = shared
- spec_source = social
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
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
