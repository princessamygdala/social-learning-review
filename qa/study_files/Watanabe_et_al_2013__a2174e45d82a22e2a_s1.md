# Watanabe et al. (2013)

- **study_id:** `a2174e45d82a22e2a_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Watanabe, N., Sakagami, M., & Haruno, M. (2013). Reward prediction error signal enhanced by striatum-amygdala interaction explains the acceleration of probabilistic reward learning by emotion. *The Journal of Neuroscience*, *33*(10), 4487-4493. https://doi.org/10.1523/JNEUROSCI.3400-12.2013
- **citation_short:** Watanabe et al. (2013)
- **doi:** 10.1523/JNEUROSCI.3400-12.2013
- **publication_type:** peer-reviewed journal
- **year:** 2013.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** CenterforInformationandNeuralNetworks,NationalInstituteofInformationandCommunicationsTechnology,Suita,Osaka565-0871,Japan,; UniversityBrainScienceInstitute,Machida,Tokyo194-8610,Japan,3JapanSocietyforPromotionofScience,and4GraduateSchoolof; University,Osaka,Suita,Osaka565-0871,Japan,and5PRESTO,JapanScienceandTechnologyAgency,Kawaguchi,; ethicscommitteeoftheNationalInstituteofInfor-; ethatlearningisaffectedbyfeelingsoften- etal; etherthepresentationofatask-; ethevisualcue(250ms); University1-3Yama-; emails: mharuno@nict.go.jp
- **code_url:** 

## Computational level
- **study_focus:** Emotional modulation of reward prediction error learning — how task-independent emotional faces (fearful vs neutral) accelerate probabilistic cue-reward association learning by enhancing RPE signals via striatum-amygdala interaction.
- **study_focus_short:** Emotional modulation of reward prediction error learning
- **learning_mode_description:** - Learning mode: Learning cue-reward associations, with emotional face modulating learning rate   - Learning from:     - Source type (non-social): world       - Source content (non-social): outcome (probabilistic monetary reward)     - Source type (social): other (emotional face of stranger)       - Source content (social): stimulus (fearful vs neutral facial expression)   - Learning about:     - Target type (non-social): world       - Target content (non-social): stimulus-outcome associations (cue-reward contingencies)
- **task_description:** Participants learned probabilistic associations (65%/35%) between four visual cues and two reward amounts (¥100 or ¥1) by trial and error. Before each cue, a task-independent fearful or neutral face was presented; participants pressed a button indicating which reward they expected, and the actual reward was shown regardless of choice (classical conditioning).
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), no interactive partner
- **n_players:** single agent (1)
- **partner_type:** human (recorded)
- **stimuli:** Visual cues (abstract), fearful and neutral facial expressions (NimStim), monetary reward outcomes (¥100 or ¥1)
- **method:** fMRI / behavioural
- **method_full:** fMRI (behavioural experiment N=20; fMRI experiment N=34)
- **main_result:** - Fearful faces accelerated probabilistic reward learning compared to neutral faces (ANOVA main effect of emotion: F(1,19) = 4.618, p = 0.045) - Exponential curve fitting showed faster learning speed for fearful vs neutral condition (F(1,19) = 6.597, p = 0.019) - RL model: learning rate higher for fearful (α_F = 0.038) vs neutral (α_N = 0.010) condition (Wilcoxon Z = -2.053, p = 0.040) - RPE signal in ventral striatum enhanced in fearful vs neutral condition (paired t(33) = 2.132, p = 0.041 in 10mm ROI; paired t(33) = 2.409, p = 0.022 in anatomical NAcc ROI) - Bilateral amygdala showed greater activity for fearful vs neutral faces (paired t(33) = 3.64, p < 0.001, anatomical ROI) - PPI analysis: amygdala activity modulated RPE-correlated striatal activity (left vStr: t = 3.02, p = 0.001; right dorsal striatum: t = 3.59, p < 0.001)
- **effect_size:** - Learning rate fearful: α_F = 0.038 ± 0.011 (SEM); neutral: α_N = 0.010 ± 0.004 (Wilcoxon Z = -2.053) - No Cohen's d, r², or η² explicitly reported; only F-values, t-values, and Z-values provided
- **learning_from:** World; probabilistic monetary reward outcomes on visual cues, modulated by emotional faces from others (fearful vs neutral)
- **learning_about:** World; cue-reward associations (which cue predicts which reward magnitude)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Rescorla-Wagner with learning rate and ¥100 bias (α, β, b) — selected by AIC. Simpler α, β model selected by BIC. Both yield consistent results on emotion effect.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "αβ", "family": "Rescorla-Wagner", "n_params": 2, "metric": "AIC/BIC"} - {"name": "αβγ", "family": "Rescorla-Wagner", "n_params": 3, "metric": "AIC/BIC"} - {"name": "αβb", "family": "Rescorla-Wagner", "n_params": 3, "metric": "AIC/BIC"} - {"name": "αβγb", "family": "Rescorla-Wagner", "n_params": 4, "metric": "AIC/BIC"}
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): controls effect of RPE on value updating. Fearful: 0.038 ± 0.011; Neutral: 0.010 ± 0.004 - β (exploration/inverse temperature): controls choice determinism. Fearful: 9.917 ± 2.246; Neutral: 14.556 ± 1.920 - b (¥100 bias): value-independent bias toward ¥100 choice. Fearful: -0.211 ± 0.080; Neutral: not significantly different from 0 - γ (reward sensitivity): transforms actual reward to subjective reward (in αβγ and αβγb models; not in winning model by BIC)
- **social_param:** None explicitly. The social manipulation (fearful face) is a task design variable, not a model parameter. The learning rate α varies by emotion condition but is not parameterized as a social parameter within the model.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC and BIC
- **how_model_fit:** individual-level-fit (maximum likelihood estimation using MATLAB fmincon, per participant)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors for value and RPE) + PPI
- **contrast:** - RPE at outcome timing: Fearful > Neutral, masked by common regions (p < 0.005): right vStr (18, 16, -4), left vStr (-20, 14, -8) - Face timing: Fearful > Neutral: bilateral amygdala (L: -28, 0, -10; R: 20, -6, -10), inferior frontal triangularis (R: 56, 34, 8) - PPI (amygdala × [Fear RPE > Neutral RPE]): dorsal striatum (R: 10, 16, 12), ventral striatum (L: -6, 10, 2) - Split analysis RPE (R-V): Fear > Neutral in right vStr (16, 18, -4; t(33) = 3.27) - Expected value: left putamen (-30, 12, -4; no emotion difference)
- **key_regions:** Emotion-enhanced RPE in bilateral ventral striatum (NAcc); fearful face processing in bilateral amygdala; striatum-amygdala functional coupling via PPI linking amygdala face-timing activity to RPE-correlated vStr activity.
- **key_regions_abbrev:** VS, NAcc, striatum, ACC, amygdala
- **coordinates_peak:** A - Prediction error (common fearful+neutral): - Ventral striatum R: 18, 16, -4 - Primary motor area L: -42, -10, 54 - Inferior frontal operculum L: -44, 6, 30 - Primary motor area R: 46, -8, 56 - Cuneus L: -8, -88, 40  D - Expected value (common): - Putamen L: -30, 12, -4 - Anterior cingulate R: 14, 48, 26  E - Face timing (Fear > Neutral): - Inferior frontal triangularis R: 56, 34, 8 - Amygdala L: -28, 0, -10 - Amygdala R: 20, -6, -10  F - PPI (Fear > Neutral × amygdala): - Dorsal striatum R: 10, 16, 12 - Ventral striatum L: -6, 10, 2  B - Reward size (common): - Calcarine sulcus L: -14, -90, -6 - Lingual gyrus R: 18, -88, -4  C - Constant at outcome (common): - Middle occipital lobe L: -20, -92, 4 - Inferior occipital lobe R: 32, -84, -6 - Primary motor area R: 46, 8, 32 - Insula cortex L: -28, 24, 0 - Primary motor area L: -44, 4, 30 - Supplementary motor area R: 8, 20, 46 - Pallidum L: -10, 6, -4 - Pallidum R: 10, 6, -6 - Middle frontal lobe L: -26, 54, 14 - Insula cortex R (Fear > Neutral): 30, 18, -16
- **analysis_type:** both (whole-brain search with ROI confirmation using anatomical masks from IBASPM/AAL and 10mm sphere ROIs via MarsBar)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N=20 (10 male, 10 female; mean age 20.0 ± 0.7) for behavioural experiment; N=34 (17 male, 17 female; mean age 19.8 ± 1.2; all right-handed) for fMRI experiment (from original 58, after pre-scan learning criterion)
- **population_category:** healthy adults
- **population_age_range:** M=20.0
- **ecological_validity:** Low — abstract cue-reward associations in a scanner; emotional faces are task-independent and have no actual relationship to reward outcomes; classical conditioning paradigm rather than interactive social learning. The faces serve as emotional modulators rather than social signals in a truly social context.
- **eligibility_flag:** Borderline — the "social" element is limited to emotional face presentation as a task-independent modulator of non-social reward learning. The learning itself is about cue-reward associations (non-social). Faces are used as emotional stimuli, not as social information sources. This is more accurately emotional modulation of learning than social learning per se. Flag: "borderline social context — emotional face modulates non-social reward learning; no social learning per se
- **concerns:** - The fMRI experiment was conducted AFTER learning was complete (participants confirmed already-learned associations during scanning), so the RPE signals are post-learning rather than during learning - Uncorrected thresholds used throughout (p < 0.001 or p < 0.005 uncorrected with 15-voxel cluster threshold) — no correction for multiple comparisons - No formal model validation (posterior predictive checks, parameter recovery, or model recovery) - AIC and BIC disagree on winning model (αβb by AIC, αβ by BIC) - The "social" aspect is minimal — facial expressions serve as emotional stimuli, not social information - No effect sizes beyond F/t/Z statistics reported
- **limitations_reported:** The dynamic property of the modulation during learning remains an open question for future study; difficulty drawing strong conclusions regarding causality with fMRI; subjects simply confirmed already learned associations in fMRI experiments, creating a possibility that behavioral and fMRI results do not have one-to-one interpretation
- **limitations_categorized:** limited ecological validity; correlational (no causal inference from fMRI); post-learning fMRI design; no correction for multiple comparisons; task simplicity
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
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `social_param`: LOW — no explicit social parameter in the model; emotion condition is a design variable, not a fitted parameter - `eligibility_flag`: MEDIUM — borderline social learning; emotional faces as modulators rather than social learning sources - `effect_size`: MEDIUM — no standard effect sizes (d, r², η²) reported; only F, t, Z statistics available - `winning_model`: MEDIUM — AIC and BIC disagree (αβb vs αβ); paper reports both
- **cannot_find:** - Standard effect sizes (Cohen's d, η², r²) — not reported - Code or data sharing links — not mentioned - Supplement — no supplement file found in the papers folder
- **other_notes:** This paper examines how emotion (fearful faces) modulates non-social probabilistic reward learning. The "social" element is limited to the use of facial expressions as emotional stimuli. The learning itself is classical conditioning of cue-reward associations, not social learning. The paper is relevant to the review insofar as it demonstrates how social stimuli (faces) can modulate basic learning mechanisms (RPE), but it is borderline for inclusion as "social learning." The fMRI design separates learning from scanning — participants learn first, then are scanned during confirmation trials, which is an important methodological consideration.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = partly
- spec_depth = general
- spec_locus = source+target
- spec_neural = shared
- spec_source = partly
- tax_domain_B_inference_modelling_others
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = emotion_inference
- tax_rr_secondary_topic = threat_fear
- tax_rr_topic_emotion_inference
- tax_rr_topic_threat_fear
- tax_topic_emotion_inference
- tax_topic_threat_fear
