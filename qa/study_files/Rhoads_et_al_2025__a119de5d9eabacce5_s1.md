# Rhoads et al. (2025)

- **study_id:** `a119de5d9eabacce5_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Rhoads, S. A., Gan, L., Berluti, K., O'Connell, K., Cutler, J., Lockwood, P. L., & Marsh, A. A. (2025). Neurocomputational basis of learning when choices simultaneously affect both oneself and others. *Nature Communications*, *16*, 9350. https://doi.org/10.1038/s41467-025-64424-9
- **citation_short:** Rhoads et al. (2025)
- **doi:** 10.1038/s41467-025-64424-9
- **publication_type:** peer-reviewed journal
- **year:** 2025.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** CenterforComputationalPsychiatry,IcahnSchoolofMedicineatMountSinai,NewYork,NY,USA; DepartmentofPsychiatry,IcahnSchoolofMedicineatMountSinai,NewYork,NY,USA; CentreforHumanBrainHealth,UniversityofBirmingham,Birmingham,UK; lableactionsinadomain-general expectedvaluethatguidesbehavior; DepartmentofPsychology,GeorgetownUniversity,Washington,DC,USA; Institute,IcahnSchoolofMedicineatMountSinai,NewYork,NY,USA; etherpeoplesimulatehowotherpeoplevaluetheirchoi-; DepartmentofNeuroscience,IcahnSchoolofMedicine; emails: shawn.rhoads@mssm.edu
- **code_url:** https://github.com/shawnrhoads/

## Computational level
- **study_focus:** Joint outcome learning / prosocial and antisocial learning; how people learn from outcomes that simultaneously affect self and others, and how trait psychopathy modulates this learning.
- **study_focus_short:** Joint outcome learning / prosocial and antisocial learning
- **learning_mode_description:** - Learning mode: Learning from one's own monetary outcomes for self and a partner to guide future choices that simultaneously affect both self and other   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (monetary gain/loss for self)     - Source type (social): other (anonymous study partner)       - Source content (social): outcome (monetary gain/loss for other)     - Note: outcomes are **joint** -- each choice produces simultaneous outcomes for self and other   - Learning about:     - Target type (non-social): self       - Target content (non-social): action/policy (which option to choose to maximize own outcomes)     - Target type (social): other (anonymous study partner)       - Target content (social): outcome (how choices affect other's welfare)     - Note: learning target is **joint** -- a single expected value integrating self and other outcomes
- **task_description:** Participants chose between fractal images (four-option or two-option versions), where each image was associated with independent probability distributions of gain/loss/null outcomes for self and a study partner; on each trial only the outcome for one target (self or other) was revealed, requiring participants to learn over time which options produced mutually beneficial, instrumentally harmful, altruistic, or mutually costly outcomes.
- **task_paradigm:** Prosocial choice task
- **players:** Single agent (participant), dyadic (anonymous study partner). Format: "Single agent (participant), dyadic (anonymous stranger partner)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Abstract fractal images, monetary outcomes (gain/loss/null for self and other)
- **method:** fMRI / online / behavioural
- **method_full:** fMRI (Study 2 neuroimaging subsample), behavioural (Study 1 behaviour-only), online behavioural (Study 3 two-option task)
- **main_result:** - Main Results:   - People integrate self- and other-relevant information into a single expected value per choice, updated asymmetrically via four types of prediction errors (target x valence) -- value integration model (Model 4) wins over value simulation models across all samples (protected exceedance probability)   - Self-benefiting bias: participants exhibited higher self-relevant than other-relevant learning rates (four-option: b = 0.82, SE = 0.17, Z = 4.96, p < .001; two-option: b = 2.09, SE = 0.17, Z = 12.46, p < .001)   - Positivity bias: higher learning rates for positive than negative PEs (four-option: b = 0.35, SE = 0.17, Z = 2.09, p = .036; two-option: b = 2.48, SE = 0.17, Z = 14.78, p < .001)   - Trait psychopathy associated with decreased other-relevant learning rates (four-option: Target x Psychopathy b = 1.42, SE = 0.53, Z = 2.68, p = .007; two-option: Target x Psychopathy b = 1.55, SE = 0.33, Z = 4.71, p < .001)   - Trait meanness (sub-factor of psychopathy) consistently predicted lower other-relevant learning (four-option: Target x Meanness b = 1.05, Z = 2.48, p = .013; two-option: Target x Meanness b = 1.09, Z = 5.32, p < .001)   - Expected value of choices encoded in bilateral mPFC, anterolateral temporal cortex, PCC (positive); bilateral anterior insula, SMA, dlPFC, precuneus, cerebellum (negative)   - Prediction errors encoded in mPFC, sgACC, ventral striatum (positive); SMA, right insula, right MCC, left fusiform (negative)   - Asymmetric value update: self-relevant positive PE encoded in bilateral VS, bilateral sgACC, bilateral amygdala, bilateral pgACC; self-relevant negative PE inversely encoded in bilateral anterior insula; other-relevant positive PE encoded in bilateral sgACC, bilateral pgACC, right VS; other-relevant negative PE encoded in right sgACC
- **effect_size:** - Self > Other learning rate (four-option): b = 0.82, Z = 4.96 - Self > Other learning rate (two-option): b = 2.09, Z = 12.46 - Positivity bias (four-option): b = 0.35, Z = 2.09 - Positivity bias (two-option): b = 2.48, Z = 14.78 - Target x Psychopathy interaction (four-option): b = 1.42, Z = 2.68 - Target x Psychopathy interaction (two-option): b = 1.55, Z = 4.71 - Valence x Psychopathy (two-option): b = 1.25, Z = 3.77 - Target x Meanness (four-option): b = 1.05, Z = 2.48 - Target x Meanness (two-option): b = 1.09, Z = 5.32 - Left VS self+ value update: Z = 3.59; Right VS self+ value update: Z = 3.63 - Left sgACC self+ value update: Z = 2.43; Right sgACC self+ value update: Z = 2.79 - Left sgACC other+ value update: Z = 2.92; Right sgACC other+ value update: Z = 3.20 - Left AI self- value update: Z = -2.92; Right AI self- value update: Z = -2.40 - Left pgACC self+ value update: Z = 3.43; Right pgACC self+ value update: Z = 2.64 - Left pgACC other+ value update: Z = 3.55; Right pgACC other+ value update: Z = 2.60
- **learning_from:** Joint outcomes for self and other (monetary gain/loss); Source: self + other (joint)
- **learning_about:** Which actions to select to optimize outcomes for self and other; Target: self + other (joint)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** 1Q-4alpha-1beta: RW with integrated value, 4 asymmetric learning rates (alpha+_self, alpha-_self, alpha+_other, alpha-_other) and 1 inverse temperature (beta). Q(k,t+1) = Q(k,t) + alpha*_i * delta_t; delta_t = r_t - Q(k,t); softmax choice rule with single beta.
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Model 1 (1Q-1alpha-1beta)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "iBIC, LME, pseudo-R2, pxp"},   {"name": "Model 2 (1Q-2alpha_valence-1beta)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "iBIC, LME, pseudo-R2, pxp"},   {"name": "Model 3 (1Q-2alpha_target-1beta)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "iBIC, LME, pseudo-R2, pxp"},   {"name": "Model 4 (1Q-4alpha_target,valence-1beta) [WINNER]", "family": "Rescorla-Wagner", "n_params": 5, "metric": "iBIC, LME, pseudo-R2, pxp"},   {"name": "Model 5 (2Q-1alpha-1beta)", "family": "Rescorla-Wagner (value simulation)", "n_params": 2, "metric": "iBIC, LME, pseudo-R2, pxp"},   {"name": "Model 6 (2Q-2alpha_target-1beta)", "family": "Rescorla-Wagner (value simulation)", "n_params": 3, "metric": "iBIC, LME, pseudo-R2, pxp"},   {"name": "Model 7 (2Q-1alpha-2beta_target)", "family": "Rescorla-Wagner (value simulation)", "n_params": 3, "metric": "iBIC, LME, pseudo-R2, pxp"},   {"name": "Model 8 (2Q-2alpha_target-2beta_target)", "family": "Rescorla-Wagner (value simulation)", "n_params": 4, "metric": "iBIC, LME, pseudo-R2, pxp"},   {"name": "Model 9 (2Q-4alpha_target,valence-1beta)", "family": "Rescorla-Wagner (value simulation)", "n_params": 5, "metric": "iBIC, LME, pseudo-R2, pxp"},   {"name": "Model 10 (2Q-4alpha_target,valence-2beta_target)", "family": "Rescorla-Wagner (value simulation)", "n_params": 6, "metric": "iBIC, LME, pseudo-R2, pxp"},   {"name": "Model 11 (1Q-1alpha-1beta-1theta)", "family": "Rescorla-Wagner + outcome sensitivity", "n_params": 3, "metric": "iBIC, LME, pseudo-R2"},   {"name": "Model 12 (1Q-2alpha_target-1beta-1theta)", "family": "Rescorla-Wagner + outcome sensitivity", "n_params": 4, "metric": "iBIC, LME, pseudo-R2"},   {"name": "Model 13 (1Q-2alpha_valence-1beta-1theta)", "family": "Rescorla-Wagner + outcome sensitivity", "n_params": 4, "metric": "iBIC, LME, pseudo-R2"},   {"name": "Model 14 (1Q-4alpha_valence,target-1beta-1theta)", "family": "Res
- **model_mb_mf:** MF
- **model_params:** - α+_self [S]: learning rate for self-relevant positive PEs. Four-option M = 0.31, SD = 0.21; Two-option M = 0.38, SD = 0.22 - α-_self [S]: learning rate for self-relevant negative PEs. Four-option M = 0.27, SD = 0.25; Two-option M = 0.21, SD = 0.28 - α+_other [S]: learning rate for other-relevant positive PEs. Four-option M = 0.21, SD = 0.24; Two-option M = 0.14, SD = 0.16 - α-_other [S]: learning rate for other-relevant negative PEs. Four-option M = 0.22, SD = 0.26; Two-option M = 0.06, SD = 0.16 - β: inverse temperature (value not reported as mean in accessible text)
- **social_param:** α+_other (learning rate for other-relevant positive prediction errors) and α-_other (learning rate for other-relevant negative prediction errors) -- these quantify sensitivity to how choices unexpectedly help or harm another person. Lower values in individuals with higher trait psychopathy/meanness.
- **social_param_name:** α+_self
- **social_param_value:** 0.31
- **social_param_sd:** 0.21
- **social_param_range:** 
- **model_comparison_metric:** Log model evidence (LME; Laplace approximation), integrated Bayesian Information Criterion (iBIC), pseudo-R2, protected exceedance probability (pxp) via random-effects Bayesian model selection with family-level inference
- **how_model_fit:** individual-level-fit (iterative MAP with expectation maximization)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) -- GLM with parametric modulators of expected value at decision phase and prediction errors at outcome phase; additional GLMs with parametric modulators for asymmetric value updates (Q_t + alpha * delta_t) by PE type; whole-brain permutation tests (FWER p < .001) + ROI analyses with non-parametric sign-flipping (10,000 permutations, FDR q < .05)
- **contrast:** - Expected value of chosen option (parametric modulator at decision phase): positive and negative encoding - Prediction error (parametric modulator at outcome phase): positive and negative encoding - Asymmetric value update by PE type (self+, self-, other+, other-): ROI analyses in VS, sgACC, AI, amygdala, pgACC
- **key_regions:** Expected value in bilateral mPFC, anterolateral temporal cortex, PCC. Prediction errors in mPFC/sgACC/VS (positive), SMA/insula/MCC (negative). Self-relevant positive PE value update in bilateral VS, sgACC, amygdala, pgACC. Self-relevant negative PE value update (inverse) in bilateral anterior insula. Other-relevant positive PE value update in bilateral sgACC, pgACC, right VS. Other-relevant negative PE value update in right sgACC.
- **key_regions_abbrev:** mPFC, ACC, sgACC, PCC, insula, AI, amygdala
- **coordinates_peak:** Expected value (positive encoding): - L Superior Medial Gyrus: -10, 63, 15 - L Superior Frontal Gyrus: -10, 57, 42 - L Mid Orbital Gyrus: -7, 54, -4 - L Medial Temporal Pole: -49, 12, -34 - R Insula: 39, 9, 12 - R Temporal Pole: 57, 9, -1 - R Medial Temporal Pole: 57, 6, -25 - L Middle Temporal Gyrus: -64, -7, -19 - R Rolandic Operculum: 57, -34, 27 - L PCC: -16, -52, 36  Expected value (negative encoding): - R Middle Orbital Gyrus: 24, 51, -19 - R IFG (p. Orbitalis): 39, 24, -1 - L IFG (p. Triangularis): -46, 21, 27 - L Superior Medial Gyrus: -7, 18, 45 - L Insula: -31, 18, 3 - R ACC: 6, 12, 27 - R Caudate Nucleus: 12, 6, 9 - L Caudate Nucleus: -13, 3, 12 - R Middle Frontal Gyrus: 30, -1, 60 - L Precentral Gyrus: -31, -4, 54 - R Brainstem: 9, -16, -13 - R Thalamus: 18, -19, 6 - L Thalamus: -10, -19, 12 - L Hippocampus: -22, -28, -4 - R PCC: 6, -34, 27 - R Inferior Parietal Lobule: 51, -46, 51 - R Precuneus: 3, -61, 51 - L Inferior Parietal Lobule: -28, -67, 45 - R Cerebellum (VIII): 36, -70, -52 - L Cerebellum (VII): -37, -73, -55 - R Cerebellum (VI): 9, -76, -22 - L Cerebellum (VIII): -13, -76, -52  Prediction error (positive encoding): - R Rectal Gyrus: 6, 51, -13 - L Superior Frontal Gyrus: -19, 36, 45 - L Rectal Gyrus: -10, 33, -16 - L Olfactory cortex: -4, 12, -10 - L Angular Gyrus: -46, -79, 33  Prediction error (negative encoding): - R Insula: 36, 21, 6 - R MCC: 12, 18, 39 - R Posterior-Medial Frontal: 6, 9, 72 - L Fusiform Gyrus: -40, -61, -13 - L Calcarine Gyrus: -19, -70, 9  Value update across all outcomes (positive encoding): - L Mid Orbital Gyrus: -7, 57, -4 - R Mid Orbital Gyrus: 12, 45, -7 - L Mid Orbital Gyrus: -10, 36, -7 - R Superior Temporal Gyrus: 57, -31, 18  (Value update negative encoding: extensive list in Supplementary Table S9, includes bilateral frontal, insular, parietal, cerebellar regions)
- **analysis_type:** both (whole-brain FWER-corrected + ROI with FDR correction)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 208 total (after exclusions). Study 1 (four-option, behaviour-only): N = 62 (18-29 years, M = 21.31, SD = 2.45, 59.7% female). Study 2 (four-option, neuroimaging): N = 27 (19-29 years, M = 21.96, SD = 3.02, 48.1% female). Combined four-option: N = 89. Study 3 (two-option, online): N = 119 (18-31 years, M = 22.04, SD = 2.85, 42.9% female). Original recruitment: N = 220 (90 four-option, 130 two-option).
- **population_category:** healthy adults
- **population_age_range:** 18–29
- **ecological_validity:** Task uses abstract fractals with monetary outcomes, which is a simplification of real-world prosocial/antisocial scenarios. The partner was real but anonymous and unseen (except briefly in neuroimaging study). Outcomes were converted to real money, providing incentive compatibility. The task captures the key feature of real-world social decisions (joint outcomes) but lacks face-to-face interaction and the emotional/relational complexity of real prosocial or antisocial situations.
- **eligibility_flag:** 
- **concerns:** (1) The neuroimaging sample is small (N = 27), limiting power for brain-behaviour correlations (the psychopathy-VS correlation did not survive multiple comparison correction). (2) Only monetary outcomes were used; results may not generalize to other domains (e.g., physical harm). (3) One outcome was always hidden per trial, which is necessary for the modelling but introduces an artificial constraint. (4) The outcome sensitivity models (Models 11-18) could not be reliably fit for the four-option task due to convergence issues -- this limits conclusions about whether learning rate asymmetries vs. outcome sensitivity asymmetries drive the results. (5) The study partner interaction is minimal (no real social interaction).
- **limitations_reported:** Future work should investigate the computations required for multi-outcome social learning in other contexts unrelated to monetary outcomes"; "An important next step will be to examine the interaction between learning behavior and various social preferences (e.g., inequity aversion)"; "An important next step will be to test how our findings would generalize to situations where all target-relevant outcomes are observable"; neuroimaging sample is small; relationship between trait psychopathy and neural encoding of other-relevant positive PEs in left VS did not survive multiple comparison correction; the task always embedded decisions in a social context (all choices carried joint social consequences), limiting ability to fully isolate social vs. non-social components; different results might be found with physical harm (e.g., electric shock) rather than financial risk.
- **limitations_categorized:** limited ecological validity; task simplicity (monetary outcomes only); small neuroimaging sample size; limited generalizability (monetary domain only); artificial task constraints (hidden outcomes); no manipulation of social preferences; limited social interaction
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 9.5
- **wc_total:** 9.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - β (inverse temperature) mean fitted value: MEDIUM -- mean values for learning rates reported in supplement but β mean not explicitly listed in accessible text - wc_8 (posterior predictive check): MEDIUM -- parameter-behaviour correlations reported but no formal posterior predictive check described
- **cannot_find:** - Exact mean fitted value of β across samples (not reported in supplement text that was accessible)
- **other_notes:** This paper involves Patricia Lockwood (one of the co-authors listed in the CLAUDE.md instructions) as a co-author. Three pre-registered studies across two task paradigms (four-option and two-option) provide strong replication. The value integration account (single Q updated by asymmetric PEs) winning over value simulation (separate Q_self and Q_other) is a key theoretical contribution, suggesting people do not maintain separate value representations for self and other when outcomes are joint. The 18 total models tested represent an unusually thorough model comparison space. Data and code are publicly available.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- pop_psychopathy
- rr_pop_healthy_adults
- rr_pop_psychopathy
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_valence_asymmetry
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_secondary_topic = moral_harm
- tax_rr_topic_moral_harm
- tax_rr_topic_prosocial_altruism
- tax_topic_moral_harm
- tax_topic_prosocial_altruism
