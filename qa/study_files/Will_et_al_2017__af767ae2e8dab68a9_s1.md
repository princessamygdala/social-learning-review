# Will et al. (2017)

- **study_id:** `af767ae2e8dab68a9_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Will, G.-J., Rutledge, R. B., Moutoussis, M., & Dolan, R. J. (2017). Neural and computational processes underlying dynamic changes in self-esteem. *eLife*, *6*, e28098. https://doi.org/10.7554/eLife.28098
- **citation_short:** Will et al. (2017)
- **doi:** 10.7554/eLife.28098
- **publication_type:** peer-reviewed journal
- **year:** 2017.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Centre for Neuroimaging, University College London, London,; UCL Centre for Computational Psychiatry and Ageing; University College London, London, United Kingdom; ethertheywerelikedordislikedmorethanexpected; ether other people liked the participants; etheyexpectedtoreceivepositive; mitsunrestricteduseand; ethatupdatingofself-
- **code_url:** 

## Computational level
- **study_focus:** Social approval learning / self-esteem updating from social evaluative feedback
- **study_focus_short:** Social approval learning / self-esteem updating from social evaluative feedback
- **learning_mode_description:** - Learning mode: Learning from social evaluative feedback (approval/disapproval) about one's own social worth (state self-esteem)   - Learning from:     - Source type (social): other (184 strangers / raters from 4 groups)     - Source content (social): outcome (approval/disapproval feedback)   - Learning about:     - Target type (social): self     - Target content (social): state (self-evaluative belief; state self-esteem)
- **task_description:** Participants received approval (thumbs up) or disapproval (thumbs down) feedback ostensibly from 184 strangers sorted into four groups with different approval rates (85%, 70%, 30%, 15%). On each trial, participants predicted whether a rater would like them, received feedback, and every 2-3 trials reported their current self-esteem on a visual analogue scale.
- **task_paradigm:** Self-evaluation / self-esteem task
- **players:** Single agent (participant), multi-target (184 ostensible strangers; 4 groups based on approval rates)
- **n_players:** multi-target (3+)
- **partner_type:** none
- **stimuli:** Names with color-coded group cues, thumbs up/down feedback symbols, visual analogue self-esteem rating scale
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - Participants adapted predictions about being liked based on rater group (F(3,117) = 209.47, $\eta_p^2$ = 0.843)   - RW model explained choice behavior (mean $r^2$ = 0.40)   - Self-esteem changes depended on both valence (r = 0.18) and expectations (r = -0.06, after regressing out valence)   - Winning self-esteem model captured dynamic changes in self-esteem (mean $r^2$ = 0.32)   - SPEs correlated with activity in bilateral ventral striatum/sgACC (Z = 4.65, k = 1172, p = 0.005 FWE)   - Self-esteem updates correlated with vmPFC activity (BA 14m/pgACC; Z = 3.51, k = 868, p = 0.047 FWE)   - Interpersonal vulnerability associated with enhanced SPE responses in left anterior insula (Z = 4.15, k = 5463, p < 0.001 FWE)   - Vulnerability associated with greater insula-vmPFC coupling during self-esteem updates (Z = 5.16, k = 78570, p < 0.001 FWE)   - CCA yielded one significant canonical dimension linking computational parameters to symptoms (Wilks's $\lambda$ = 0.01, canonical correlation = 0.87)
- **effect_size:** $\eta_p^2$ = 0.843 (group effect on predictions); mean $r^2$ = 0.40 (RW model fit to choices); mean $r^2$ = 0.32 (self-esteem model fit); canonical correlation = 0.87 (CCA); Z = 4.65 (SPE in VS/sgACC); Z = 3.51 (self-esteem update in vmPFC); Z = 4.15 (vulnerability x SPE in insula); Z = 5.16 (vulnerability x insula-vmPFC PPI)
- **learning_from:** Other (strangers); approval/disapproval social evaluative feedback
- **learning_about:** Self; own social worth (state self-esteem)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** Exponential kernel regression: Self-esteem(t) = $w_0$ + $w_1$ $\sum_{j=1}^{t} \gamma^{t-j}$ SPE$_j$ + $\epsilon$; with SPEs derived from RW model with learning rate $\eta$, bias ESV$_0$, temperature T, and initial ESVs. 9 free parameters total.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Model 1: Learning and positive bias (WINNING)", "family": "RW + exponential kernel regression", "n_params": 9, "metric": "BIC = -633"},   {"name": "Model 2: Learning, but no bias", "family": "RW + exponential kernel regression", "n_params": 8, "metric": "BIC = -378"},   {"name": "Model 3: Correct initial beliefs about approval", "family": "Exponential kernel regression (no learning)", "n_params": 7, "metric": "BIC = 409"},   {"name": "Model 4: Separate term for expectations", "family": "RW + exponential kernel regression (separate expectation term)", "n_params": 10, "metric": "BIC = -502"},   {"name": "Model 5: Free initial beliefs about approval (self-esteem only)", "family": "Exponential kernel regression", "n_params": 5, "metric": "BIC = -5671"},   {"name": "Model 6: Outcome valence only (self-esteem only)", "family": "Exponential kernel regression (no expectations)", "n_params": 7, "metric": "BIC = -5581"} ]
- **model_mb_mf:** MF
- **model_params:** - $w_0$ (baseline self-esteem): mean = 0.73, SD = 0.16 - $w_1$ (weight on SPEs) [S]: mean = 0.04, SD = 0.03 - $\sigma$ (Gaussian noise term): mean = 0.08, SD = 0.04 - $\eta$ (learning rate): mean = 0.04, SD = 0.08 - ESV$_0$ (response bias / positive bias parameter) [S]: mean = 0.42, SD = 0.25 - T (decision temperature): mean = 0.12, SD = 0.35 - $\gamma$ (forgetting factor): mean = 0.66, SD = 0.35 - ESV$_1$(1) (initial approval belief, most positive group): fitted, value not separately reported - ESV$_4$(1) (initial approval belief, least positive group): fitted, value not separately reported - Average initial approval beliefs: mean = 0.64, SD = 0.24 - Range initial approval beliefs: mean = 0.34, SD = 0.29
- **social_param:** $w_1$ (weight on social prediction errors — captures how strongly SPEs influence self-esteem updates); ESV$_0$ (positive bias parameter — captures persistent belief about being liked/disliked, the "extra credit" people give themselves)
- **social_param_name:** $w_1$
- **social_param_value:** 0.04
- **social_param_sd:** 0.03
- **social_param_range:** 
- **model_comparison_metric:** BIC (Bayesian Information Criterion), summed across participants
- **how_model_fit:** individual-level-fit (maximum likelihood fitting with flat priors, parameters fitted per participant)
- **data_type_fit_to:** choice behavior + self-report ratings (self-esteem)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) + PPI
- **contrast:** - SPE parametric modulator at feedback onset → bilateral ventral striatum/sgACC (Z = 4.65, p = 0.005 FWE) - Self-esteem update parametric modulator at feedback onset → vmPFC (BA 14m/pgACC BA 32pl) (Z = 3.51, p = 0.047 FWE) - Interpersonal vulnerability x SPE → left anterior insula/IFG (Z = 4.15, p < 0.001 FWE) - PPI: Insula seed x self-esteem update, modulated by vulnerability → vmPFC (BA 14m) (Z = 5.16, p < 0.001 FWE)
- **key_regions:** Social prediction errors in bilateral ventral striatum/sgACC; self-esteem belief updates in vmPFC (medial OFC BA 14m extending into pgACC BA 32pl); vulnerability-modulated SPE processing in left anterior insula/IFG; vulnerability-modulated insula-vmPFC functional connectivity during self-esteem updates.
- **key_regions_abbrev:** VS, striatum, vmPFC, mPFC, OFC, ACC, sgACC, insula, AI, IFG
- **coordinates_peak:** - Ventral striatum/sgACC (left peak): -8, 21, -5 - Ventral striatum/sgACC (right peak): 5, 20, -8 - vmPFC (medial OFC BA 14m / pgACC BA 32pl): -6, 33, -15 - Left anterior insula / IFG: -44, 11, 9 - vmPFC (PPI, insula-vmPFC coupling): 11, 32, -11  Note: Supplementary file 2 reportedly contains a full list of activations at p < .001 uncorrected, k > 50, but is not accessible as a separate file. Coordinates above are from main text only.
- **analysis_type:** whole-brain (with PPI using 6mm sphere seed derived from whole-brain analysis)  ---  ### QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 40 (from original 44; 4 excluded for falling asleep during scanning); mean age = 23.3, SD = 3.2, 14 male
- **population_category:** healthy adults
- **population_age_range:** M=23.3
- **ecological_validity:** Moderate. The social evaluation paradigm used a cover story involving an online profile evaluated by 184 ostensible strangers, providing some ecological validity. However, feedback was computer-generated (not real social feedback), the social interaction was unidirectional, and the lab setting limits generalizability to real-world social evaluation contexts.
- **eligibility_flag:** 
- **concerns:** Feedback was entirely computer-generated (participants were deceived); CCA with 9 computational parameters and 11 symptom measures on N = 40 may be overfitted; no out-of-sample validation of the CCA dimension; no parameter recovery or model recovery reported; sample size moderate for individual-differences analyses with fMRI.
- **limitations_reported:** Authors acknowledge: the study does not disentangle separate contributions of ventral striatum and sgACC to self-related learning through interactions with others; whether psychiatric patients fall at the extreme end of the "interpersonal vulnerability" dimension remains a question for future research; the CCA-identified questionnaire weighting needs prospective validation as a predictor of mental health outcomes.
- **limitations_categorized:** limited ecological validity; no clinical sample; overfitting risk (CCA with small N); no prospective validation; no parameter recovery; no model recovery; task simplicity (unidirectional feedback)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 6.0
- **wc_total:** 6.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - coordinates_peak: MEDIUM confidence — main text coordinates extracted; Supplementary file 2 with full activation tables not accessible as a separate file - wc_guidelines rule 3 (simulate): LOW confidence — no simulation described but cannot fully rule out it was done without reporting - wc_guidelines rule 10 (transparent reporting): MEDIUM — eLife typically requires data sharing, but no explicit mention in paper text
- **cannot_find:** Full activation table from Supplementary file 2 (not available as separate file); explicit data/code sharing statement; ESV$_1$(1) and ESV$_4$(1) individual mean fitted values (only average and range reported)
- **other_notes:** This is an eLife (2017) open-access paper. The supplementary files (Supplementary file 1: profile instructions; Supplementary file 2: brain activation tables) are embedded in the eLife publication but not available as separate files in the papers folder. The paper also includes two control tasks reported in figure supplements: an "Other evaluation" control task (participants observe feedback about another person) and a Dictator Game. These control tasks are not separate studies — they serve as validation for the main fMRI task. Single study paper.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = dedicated
- spec_source = social
- spec_target = partly
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = self_esteem
- tax_rr_secondary_topic = social_approval_reward
- tax_rr_topic_self_esteem
- tax_rr_topic_social_approval_reward
- tax_topic_self_esteem
- tax_topic_social_approval_reward
