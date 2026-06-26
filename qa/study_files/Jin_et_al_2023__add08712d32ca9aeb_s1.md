# Jin et al. (2023)

- **study_id:** `add08712d32ca9aeb_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Jin, T., Zhang, S., Lockwood, P., Vilares, I., Wu, H., Liu, C., & Ma, Y. (2023). Learning whom to cooperate with: Neurocomputational mechanisms for choosing cooperative partners. *Cerebral Cortex*, *33*(8), 4612–4625. https://doi.org/10.1093/cercor/bhac365
- **citation_short:** Jin et al. (2023)
- **doi:** 10.1093/cercor/bhac365
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** LaboratoryofCognitiveNeuroscienceandLearningandIDG/McGovernInstituteforBrainResearch,BeijingNormalUniversity,Beijing100875,China,; CentreforHumanBrainHealthandInstituteforMentalHealth,SchoolofPsychology,UniversityofBirmingham,Birmingham,B152TT,UnitedKingdom,; CenterforCollaborationandInnovationinBrainandLearningSciences,BeijingNormalUniversity,Beijing100875,China,; CentreforCognitiveandBrainSciencesandDepartmentofPsychology,UniversityofMacau,Taipa,MacauSAR,519000,China,; DepartmentofPsychology,UniversityofMinnesota,75EastRiverRoad,Minneapolis,MN,55455,UnitedStates,; LaboratoryofBrainImagingand
- **code_url:** 

## Computational level
- **study_focus:** Cooperation learning — learning others' cooperativeness through trial-and-error for self and vicariously for another person.
- **study_focus_short:** Cooperation learning
- **learning_mode_description:** - Learning mode: Learning from partners' cooperative/defective actions about their cooperativeness, for oneself and vicariously for another person.   - Learning from:     - Source type (social): other (cooperation partner)     - Source content (social): action/policy (cooperate vs. defect)   - Learning about:     - Target type (social): other (cooperation partner)     - Target content (social): state (mental state; cooperativeness trait)
- **task_description:** In a modified prisoner's dilemma task during fMRI, participants chose one of two gender-matched partners to cooperate with (one 70% cooperative, one 30% cooperative) across 160 trials, half for themselves and half vicariously for a gender-matched stranger. Participants cooperated by default and learned which partner was more cooperative through trial-and-error feedback.
- **task_paradigm:** Prisoner's dilemma
- **players:** Single agent (participant), multi-target (4 pairs of partners; choices made for self and for a gender-matched stranger confederate)
- **n_players:** multi-target (3+)
- **partner_type:** confederate
- **stimuli:** Face photographs of gender-matched partners, binary cooperation/defection outcomes, monetary points (200 mutual cooperation; 300 for defector, 0 for agent if partner defects)
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Participants learned to choose cooperative partners above chance for both self (71.55% +/- 3.04%) and other (68.22% +/- 3.00%) conditions (both p < 0.001) - Faster learning criterion reached for self vs. other (self: 14.93 +/- 1.62 trials; other: 18.45 +/- 1.82; t(27) = -2.196, p = 0.037, 95% CI [-6.805, -0.230]) - Higher stay probability for self than other (self: 74.64%; other: 67.40%; t(27) = 2.944, p = 0.007, 95% CI [2.19%, 12.28%]) - Faster RT for self than other (self: 1.212s; other: 1.259s; t(27) = 2.817, p = 0.009) - Empathic concern positively associated with RT difference between other and self (r = 0.433, p = 0.021) - Learning rates similar for self and other (self: 0.275; other: 0.274; V = 212, p = 0.849; BF[H1:H2] = 6.852) - Inverse temperature significantly higher for self than other (self: 3.91; other: 3.30; V = 295, p = 0.036) - pgACC tracked PEs in both self and other conditions (self: t = 3.99, p < 0.001; other: t = 3.55, p = 0.001; BF[H1:H2] = 6.791) - Right striatum encoded PEs only for self (t = 4.35, p < 0.001), not other (t = 1.47, p = 0.15); self vs. other: t = 2.64, p = 0.014 - Empathic concern associated with striatal other-vs-self PE encoding (left: r = 0.41, p = 0.030; right: r = 0.52, p = 0.005) - MVPA: rTPJ classification accuracy of self vs. other outcomes correlated with inverse temperature difference (r = 0.473, p = 0.011)
- **effect_size:** - Learning criterion self vs. other: t(27) = -2.196, 95% CI [-6.805, -0.230] - Stay probability self vs. other: t(27) = 2.944, 95% CI [2.19%, 12.28%] - RT self vs. other: t(27) = 2.817, 95% CI [-0.083s, -0.013s] - Empathic concern x RT difference: r = 0.433 - Empathic concern x RT (multiple regression): beta = 0.011, SEM = 0.004, t = 2.564 - Inverse temperature self vs. other: V = 295 - pgACC PE self: t = 3.99, 95% CI [0.29, 0.90]; other: t = 3.55, 95% CI [0.24, 0.90] - R striatum PE self vs. other: t = 2.64, 95% CI [0.16, 0.75] - Empathic concern x R striatum: r = 0.52 - rTPJ MVPA x inverse temperature difference: r = 0.473 - Cooperative rating interaction (time x propensity): partial eta-squared = 0.45
- **learning_from:** Other (cooperation partner); partner's cooperative vs. defective actions
- **learning_about:** Other (cooperation partner); cooperativeness (trait)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** RW with separate parameters for self and other (2 LRs: alpha_self, alpha_other; 2 betas: beta_self, beta_other) — Model M3
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** | Model | Family | n_params | iBIC | |-------|--------|----------|------| | M1: No-learning (beta only) | Baseline | 1 | 6141.4 | | M2: Basic RW (shared alpha, beta) | Rescorla-Wagner | 2 | 4694.1 | | M3: RW separate alpha_self, alpha_other, beta_self, beta_other | Rescorla-Wagner | 4 | 4667.5 | | M4: RW separate alpha_cooperate, alpha_defect, shared beta | Rescorla-Wagner | 3 | 4691.7 | | M5: RW separate alpha_C_self, alpha_C_other, alpha_D_self, alpha_D_other, beta_self, beta_other | Rescorla-Wagner | 6 | 4669.7 | | M6: Basic RW + lapse (shared) | Rescorla-Wagner | 3 | 4705.3 | | M7: RW + lapse (separate for self/other) | Rescorla-Wagner | 6 | 4668.8 |
- **model_mb_mf:** MF
- **model_params:** - alpha_self [S]: learning rate for self condition (mean = 0.275 +/- 0.04) - alpha_other [S]: learning rate for other condition (mean = 0.274 +/- 0.04) - beta_self [S]: inverse temperature for self condition (mean = 3.91 +/- 0.32) - beta_other [S]: inverse temperature for other condition (mean = 3.30 +/- 0.28)
- **social_param:** alpha_other (learning rate for vicarious/other condition); beta_other (inverse temperature for vicarious/other condition). The self-other split of learning rate and inverse temperature captures how learning computations differ when choosing cooperative partners for oneself vs. for another person.
- **social_param_name:** alpha_self
- **social_param_value:** 0.275
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** integrated Bayesian Information Criterion (iBIC)
- **how_model_fit:** Individual-level fit via hierarchical Bayesian approach using expectation-maximization (EM) algorithm to find MAP estimates with group-level priors
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) + MVPA (whole-brain searchlight SVM)
- **contrast:** - Self condition: cooperative PE parametric modulator (pgACC, striatum, precentral gyrus) - Other condition: cooperative PE parametric modulator (pgACC) - Conjunction: self PE ∩ other PE (pgACC) - Self > Other PE (bilateral striatum) - MVPA 1: self vs. other choice decoding (dlPFC, TPJ, occipital cortex, SFG/MFG) - MVPA 2: self vs. other outcome decoding (rTPJ, L striatum, dACC, PCUN, PCC, STG)
- **key_regions:** pgACC tracked PEs for both self and other; bilateral striatum encoded PEs preferentially for self; rTPJ discriminated self vs. other outcomes (MVPA) and correlated with exploitation tendency; dlPFC and lTPJ discriminated self vs. other choices (MVPA); dACC distinguished self/other outcomes (MVPA). Empathic concern modulated striatal self-other PE encoding.
- **key_regions_abbrev:** striatum, dlPFC, dACC, ACC, TPJ
- **coordinates_peak:** *Table S1 — Model-based fMRI: PE*  Self Condition: Cooperative PE: - pgACC: 0, 42, 6 (L/R; t = 6.68, k = 602) - Striatum (L): -12, 9, -3 (t = 6.30, k = 61) - Precentral gyrus (L): -6, -33, 54 (t = 5.91, k = 641) - Cuneus/Middle Occipital Gyrus (R): 18, -93, 12 (t = 5.47, k = 159) - Extra-Nuclear/Putamen (L): -27, -15, 0 (t = 5.34, k = 193) - Occipital Lobe (L): -15, -96, 9 (t = 4.84, k = 62)  Other Condition: Cooperative PE: - pgACC (R): 9, 30, 9 (t = 4.69, k = 128)  Conjunction (self ∩ other PE): - pgACC: -3, 39, 0 (t = 4.65, k = 104) [FWE-SVC]  Self > Other PE: - Striatum (L): -18, 9, -3 (t = 3.75, k = 2) [FWE-SVC] - Striatum (R): 18, 6, -6 (t = 3.60, k = 3) [FWE-SVC]  *Table S2 — MVPA: Self vs. Other outcome decoding* - rTPJ (R): 45, -30, 21 (t = 5.58, k = 543) - Striatum/Insula (L): -21, 6, 6 (t = 5.14, k = 401) - Superior Parietal Lobe/Precuneus (L): -18, -51, 57 (t = 5.35, k = 689) - PCC/Corpus Callosum (L): -6, -42, 6 (t = 5.04, k = 225) - Middle Cingulate Cortex/SFG (L/R): 0, 21, 45 (t = 5.04, k = 526) - STG (L): -48, -21, 6 (t = 4.49, k = 196)  *MVPA: Self vs. Other choice decoding (from main text)* - dlPFC (L): -33, 30, 30 (t = 4.93, k = 39) - Occipital cortex/lTPJ: 0, -84, 6 (t = 8.99, k = 4300) - rMTG/rTPJ (R): 48, -51, 3 (t = 5.24, k = 179) - SFG/MFG (L): -18, 24, 54 (t = 5.36, k = 326)
- **analysis_type:** both (whole-brain FWE-corrected + ROI/SVC for pgACC and striatum)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 28 (12 males; age range 19–27, M = 22.25, SD = 2.40); 32 recruited, 4 excluded (1 technical failure, 3 excessive head motion)
- **population_category:** healthy adults
- **population_age_range:** 19–27
- **ecological_validity:** Laboratory-based task with relatively simple binary cooperation/defection structure; uses face photographs of partners which adds some ecological validity; modified prisoner's dilemma paradigm is stylized but captures essential features of partner selection. Limited by lack of real interactive partners (preprogrammed probabilities), no option to defect, and purely monetary outcomes.
- **eligibility_flag:** 
- **concerns:** - Relatively small sample (N = 28) for fMRI, acknowledged by authors - Partners were preprogrammed (not real interactive agents) — reduces ecological validity - No non-social control condition to isolate social-specific PE signals - SVC corrections for striatum and pgACC based on a priori hypotheses (Neurosynth-derived ROI for striatum) - MVPA choice decoding required unusually stringent threshold (p < 0.0001) due to one massive cluster at standard threshold - No option to defect limits generalizability to real cooperation scenarios
- **limitations_reported:** Only involved personal and vicarious learning in the social context — no non-social control condition to test whether same brain regions support non-social learning; participants could only choose whom to cooperate with, not whether to cooperate or defect — unknown whether basic RL would suffice in more complex cooperation scenarios (e.g. 2-stage games); cautious about decoding results due to relatively small sample size; classification performance variance is relatively high for small sample sizes.
- **limitations_categorized:** limited ecological validity; task simplicity; sample size; no non-social control condition; limited generalizability
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 7.0
- **wc_total:** 7.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - wc_3 (MEDIUM): Simulation was done post-hoc with fitted parameters as posterior predictive check, not a priori design verification - preregistered (MEDIUM): No mention found in main text or supplement — coded as "Not reported" - ecological_validity (MEDIUM): Assessment inferred from task description, not explicitly discussed as such by authors
- **cannot_find:** - No explicit data/code sharing statement found - No preregistration statement found - No parameter recovery or model recovery analyses
- **other_notes:** Patricia Lockwood is a co-author on this paper. The EM-based hierarchical Bayesian fitting approach references Huys et al. (2011) methodology. ROIs for pgACC defined from Lau et al. (2020); striatum ROI from Neurosynth "prediction error" term-based meta-analysis. All model parameters are technically "social" since the task is entirely in a social cooperation context; the [S] tags mark the other-specific parameters.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = cooperation
- tax_rr_secondary_topic = reputation_learning
- tax_rr_topic_cooperation
- tax_rr_topic_reputation_learning
- tax_topic_cooperation
- tax_topic_reputation_learning
