# Wieland et al. (2023)

- **study_id:** `afafb165757dcce50_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Wieland, L., Ebrahimi, C., Katthagen, T., Panitz, M., Luettgau, L., Heinz, A., Schlagenhauf, F., & Sjoerds, Z. (2023). Acute stress alters probabilistic reversal learning in healthy male adults. *European Journal of Neuroscience, 57*(5), 824--839. https://doi.org/10.1111/ejn.15916
- **citation_short:** Wieland et al. (2023)
- **doi:** 10.1111/ejn.15916
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** InstituteofPsychology&Leiden Behavioural adaptation is a fundamental cognitive ability, ensuring survival by; InstituteofPsychology&LeidenInstituteforBrainandCognition,LeidenUniversity,Leiden,theNetherlands; DepartmentofPsychiatryandNeurosciences,CCM,Charité-UniversitätsmedizinBerlin,Berlin,Germany; UniversityCollegeLondonCentreforComputationalPsychiatryandAgeingResearch,London,UK; etherlands MRI(fMRI)inawithin-subjectsdesigntoinvestigatetheeffectofacutepsycho-; CenterforNeurosciencesBerlin,Charité-UniversitätsmedizinBerlin,Berlin,Germany; InstituteforHumanCognitiveandBrainSciences,Leipzig,Ger
- **code_url:** 

## Computational level
- **study_focus:** Reversal learning under acute psychosocial stress -- how stress modulates reward prediction error-driven learning and its neural correlates during probabilistic reversal learning.
- **study_focus_short:** Reversal learning under acute psychosocial stress -- how stress modulates
- **learning_mode_description:** - Learning mode: Learning from one's own reward/punishment outcomes about stimulus-action-outcome contingencies under stress   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (monetary win/loss feedback)   - Learning about:     - Target type (non-social): world (stimulus-reward contingencies)     - Target content (non-social): state (reward probabilities of choice options)
- **task_description:** In a within-subjects design, participants chose between two cards with anti-correlated probabilistic reward contingencies (80/20) that reversed four times across 160 trials, once after the Trier Social Stress Test and once after a control condition. They received monetary feedback (win/loss of 10 cents) on each trial.
- **task_paradigm:** Reversal learning
- **players:** Single agent (participant), no social interaction partner during task
- **n_players:** single agent (1)
- **partner_type:** unclear
- **stimuli:** Abstract geometric figures on cards, binary monetary feedback (10 cent coin / crossed-out coin)
- **method:** fMRI
- **method_full:** fMRI (model-based fMRI with parametric regressors)
- **main_result:** - Stress slightly increased correct response rates (OR = 1.13, CI: 1.02--1.24) - Cortisol as continuous predictor also predicted correct responses (OR = 1.09, CI: 1.01--1.17) - Winning model: RW-DU-2al with stress affecting only temperature parameters (PXP = 0.92) - Loss learning rate higher than win learning rate (t(27) = -6.7) - Choice temperature higher after win vs. loss trials (F(1,27) = 22.77) - Main effect of RPE across conditions in vmPFC, bilateral ventral striatum, PCC, bilateral insula (pFWE < 0.05 whole-brain) - Stress > control: stronger RPE coding for win trials in left striatum (t = 6.43, pFWE = 0.041) - With order modelling: stress reduced choice stochasticity (stress scaling win t(27) = 7.1; stress scaling loss t(27) = 6.6)
- **effect_size:** - Condition effect on correct responses: OR = 1.13 - Cortisol effect on correct responses: OR = 1.09 - Subjective arousal stress response: d = 0.9 - Subjective valence stress response: d = 0.8 - Subjective stress response: d = 1.3 - Cortisol stress response: d = 0.5 - Marginal/conditional R2 for correct responses model: 0.053/0.088
- **learning_from:** Self; own monetary win/loss feedback on chosen card
- **learning_about:** World; stimulus-reward contingency structure (which card is better)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** RW double-update, 2 learning rates, stress scaling on betas: RW-DU-2al-StressBetas (alpha_win, alpha_loss, beta_control_win, beta_control_loss, beta_stress_win, beta_stress_loss; 6 free params)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** Step 1 (control condition): 1. {"name": "RW-SU-1al", "family": "Rescorla-Wagner", "n_params": 3, "metric": "PXP"} 2. {"name": "RW-SU-2al", "family": "Rescorla-Wagner", "n_params": 4, "metric": "PXP"} 3. {"name": "RW-DU-1al", "family": "Rescorla-Wagner", "n_params": 3, "metric": "PXP"} 4. {"name": "RW-DU-2al", "family": "Rescorla-Wagner", "n_params": 4, "metric": "PXP (winner, PXP=0.62)"} 5. {"name": "RW-iDU-1al", "family": "Rescorla-Wagner", "n_params": 4, "metric": "PXP"} 6. {"name": "RW-iDU-2al", "family": "Rescorla-Wagner", "n_params": 5, "metric": "PXP"} 7. {"name": "PH", "family": "Pearce-Hall", "n_params": 3, "metric": "PXP"} 8. {"name": "No-learning", "family": "null", "n_params": 1, "metric": "PXP"}  Step 2 (stress effects on winning model): 1. {"name": "RW-DU-2al-NoStress", "family": "Rescorla-Wagner", "n_params": 4, "metric": "PXP"} 2. {"name": "RW-DU-2al-StressLearning", "family": "Rescorla-Wagner", "n_params": 6, "metric": "PXP"} 3. {"name": "RW-DU-2al-StressBetas", "family": "Rescorla-Wagner", "n_params": 6, "metric": "PXP (winner, PXP=0.92)"} 4. {"name": "RW-DU-2al-StressAll", "family": "Rescorla-Wagner", "n_params": 8, "metric": "PXP"}
- **model_mb_mf:** MF
- **model_params:** - alpha_win: learning rate for win trials (M = 0.19, SD = 0.11) - alpha_loss: learning rate for loss trials (M = 0.36, SD = 0.17) - beta_control_win: inverse temperature for win trials, control (M = 6.01, SD = 3.99) - beta_control_loss: inverse temperature for loss trials, control (M = 3.21, SD = 2.52) - beta_stress_win: inverse temperature for win trials, stress (M = 5.61, SD = 4.68) - beta_stress_loss: inverse temperature for loss trials, stress (M = 3.08, SD = 3.33)  No parameters marked [S] -- no social parameters in the model.
- **social_param:** None -- no social parameter in the model.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Protected exceedance probability (PXP) from hierarchical Bayesian model comparison (cbm toolbox)
- **how_model_fit:** Individual-level fit via hierarchical Bayesian inference (cbm toolbox; Piray & Daw, 2020)
- **data_type_fit_to:** Choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors -- model-derived RPE as parametric modulator)
- **contrast:** - Main effect of RPE across both conditions (vmPFC, VS, PCC, insula; pFWE < 0.05 whole-brain) - Stress > Control: RPE win trials in left striatum ([-10, 10, -2], t = 6.43, pFWE = 0.041) - Stress > Control: RPE combined win+loss -- right insula trend (t = 4.02, pFWE SVC = 0.068) - No significant stress effect for loss trial RPEs
- **key_regions:** RPE main effect in vmPFC, bilateral ventral striatum, PCC, bilateral insula. Stress enhanced positive RPE coding for win trials in left ventral striatum.
- **key_regions_abbrev:** VS, striatum, vmPFC, mPFC, PCC, insula, AI
- **coordinates_peak:** - Middle frontal gyrus (L): 10, 42, -12 - Middle frontal gyrus (R): 4, 40, -12 - ACC pregenual (L): -2, 48, -4 - Posterior cingulate cortex (L): -8, -52, 32 - Precuneus (L): -2, -56, 26 - Precuneus (L): 0, -56, 18 - Ventral striatum (R): 10, 2, -12 - Ventral striatum (R): 10, 10, -10 - Insula (L): -36, 2, 12 - Insula (L): -36, -6, 18 - IFG pars orbitalis (L): -22, 32, -12 - Ventral striatum (L): -10, -6, -10 - Putamen (L): -32, -12, 2 - Insula (R): 38, 6, 12  Stress > Control, RPE win trials: - Left striatum: -10, 10, -2  Stress > Control, RPE combined (trend): - Right insula: 46, 4, 10
- **analysis_type:** Both (whole-brain FWE corrected for main effects; SVC mask of main task effect for condition contrasts)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 28 (final analyzed; from initial 38; all male, right-handed; mean age 26.9, SD = 5.7, range 18--41)
- **population_category:** healthy adults
- **population_age_range:** M=26.9
- **ecological_validity:** Low -- abstract card-choice task with probabilistic monetary feedback, no real social interaction during the learning task itself. The stress induction (TSST) is a well-validated psychosocial stressor but the reversal learning task is non-social.
- **eligibility_flag:** The learning task itself is non-social (probabilistic reversal learning with abstract stimuli and monetary outcomes). The stress induction (TSST) is psychosocial, but the learning process does not occur in a social context. Flag: "Stressor is psychosocial (TSST), but the learning task is non-social reversal learning -- borderline social context.
- **concerns:** - Very low statistical power (power = 0.46 by authors' own analysis for expected effect size) - Male-only sample limits generalizability - Homogeneous sample (young, highly educated) - Step 1 winning model PXP = 0.62 is relatively low - Task does not disentangle value representation from RPE at feedback - Order effects not modeled in primary analysis (addressed in supplementary)
- **limitations_reported:** Low power due to small sample size (N=28, power=0.46); male-only sample limits generalizability across sex and gender; homogeneously young and highly educated sample; task does not temporally disentangle value and RPE representations in the brain; stress effects may relate to value representation rather than RPE; between-condition differences in probabilistic feedback events required exclusion of 6 participants; effects should be replicated independently
- **limitations_categorized:** Sample size; limited generalizability (sex/gender); limited generalizability (age/education); task simplicity; confound between value and RPE; low power
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
- **wc_rule10:** Yes
- **wc_score:** 6
- **wc_total:** 6.0

## Context flags
- **ctx_copresence:** unclear
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - eligibility_flag: MEDIUM -- the TSST is a psychosocial stressor, but the learning task itself involves no social interaction or social learning target - social_param: HIGH -- confirmed no social parameters, model is purely reward-learning - wc_3 (simulate): MEDIUM -- no explicit mention of simulation before fitting; could have been done but not reported - Step 1 winning model PXP: MEDIUM -- PXP = 0.62 is modest evidence
- **cannot_find:** - No explicit effect sizes (Cohen's d) for fMRI contrasts in main text or supplement (only t-values and p-values reported for neuroimaging) - No posterior predictive checks - No parameter or model recovery analyses
- **other_notes:** The stress manipulation is psychosocial (TSST with mock interview committee), making the overall study design social in the stress induction but not in the learning task. Data and code available at https://github.com/agschlagenhauf/SALAD. The supplementary analysis controlling for order effects confirmed stress scaling on betas (PXP = 0.96) and showed stress reduced choice stochasticity. The supplement provides a comprehensive coordinate table for the main RPE effect (Table S-E) with whole-brain FWE-corrected results.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- pop_stress
- rr_pop_healthy_adults
- rr_pop_stress
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = general
- spec_locus = source
- spec_neural = shared
- tax_domain_G_uncertainty_volatility
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = G_uncertainty_volatility
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_temperature
- tax_rr_primary_topic = volatility
- tax_rr_topic_volatility
- tax_topic_volatility
