# Rosenthal et al. (2019)

- **study_id:** `af233726c38e0f373_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Rosenthal, I. A., Hutcherson, C. A., Adolphs, R., & Stanley, D. A. (2019). Deconstructing theory-of-mind impairment in high-functioning adults with autism. *Current Biology*, *29*(3), 513–519. https://doi.org/10.1016/j.cub.2018.12.039
- **citation_short:** Rosenthal et al. (2019)
- **doi:** 10.1016/j.cub.2018.12.039
- **publication_type:** peer-reviewed journal---
- **year:** 2019.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** DepartmentofPsychology,UniversityofTorontoScarborough,1265MilitaryTrail,Toronto,ONM1C1A4,Canada; DepartmentofMarketing,RotmanSchoolofManagement,UniversityofToronto,Toronto,ONM5S3E6,Canada; DivisionofHumanitiesandSocialSciences,CaliforniaInstituteofTechnology,1200E; SchoolofPsychology,AdelphiUniversity,1SouthAvenue,GardenCity,NY11530,USA; etheserepresentationscontinuouslythroughoutthetrialsof; ether, these results confidence intervals [CI] [15]; ethodsfordetailsonAgent; ethodsfordescrip-; emails: dstanley@adelphi.edu
- **code_url:** https://osf.io/ahp5q/

## Computational level
- **study_focus:** Mentalizing learning / Theory-of-mind learning — decomposing ToM into belief-tracking and intention-learning components in ASD vs. controls
- **study_focus_short:** Mentalizing learning / Theory-of-mind learning
- **learning_mode_description:** - Learning mode: Learning another person's beliefs about context and their charitable intentions from observing their choices   - Learning from:     - Source type (social): other (observed agent)     - Source content (social): action/policy (agent's donation choices) and outcomes (whether computer reversed the choice)   - Learning about:     - Target type (social): other (observed agent)       - If joint: not joint     - Target content (social): state (mental state; beliefs about program mode) and state (mental state; intentions/preferences toward charities)
- **task_description:** Participants first completed a charitable donation task themselves, then observed another person (the Agent) complete the same task. On each trial, participants estimated the Agent's belief about the current program mode (normal vs. reversal), the Agent's intention (donate vs. keep), and predicted the Agent's choice, receiving feedback on the Agent's actual choice and reversal outcome.
- **task_paradigm:** Prosocial choice task
- **players:** Single agent (participant/mentalizer), single target (observed agent whose choices were replayed)
- **n_players:** single agent (1)
- **partner_type:** unclear
- **stimuli:** Pictures of agent and charities, binary choice outcomes (donate/keep), computer reversal feedback (executed/reversed), monetary amounts ($7–$13)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - ASD intent learning rate significantly lower than both CTL groups (ASD: $\lambda_I$ = 0.18, 95% CI [0.12, 0.25]; CTL1: $\lambda_I$ = 0.58, 95% CI [0.44, 0.72]; CTL2: $\lambda_I$ = 0.48, 95% CI [0.32, 0.66]; CIs non-overlapping) - Belief learning rates did not differ across groups (ASD: $\lambda_B$ = 0.56, 95% CI [0.42, 0.68]; CTL1: $\lambda_B$ = 0.49, 95% CI [0.38, 0.61]; CTL2: $\lambda_B$ = 0.63, 95% CI [0.52, 0.72]) - Out-of-sample model accuracy: CTL-fit models predicted ASD intent performance significantly worse than CTL intent performance (Intent DiffAcc = 10.4%, 95% CI [5.3%, 15.7%]) - Belief accuracy correlated with ADOS Social Affect CSS (r = -0.39, 95% CI [-0.68, -0.03]) - Intent learning correlated with ADOS Social Affect CSS (r = -0.46, 95% CI [-0.78, -0.07]) - Bayesian model comparison: M1 was winning model for CTL groups (CTL1 pxp = 0.99, bor = 5.9e-6; CTL2 pxp = 0.95, bor = 1.3e-5); ASD group was heterogeneous (M1 pxp = 0.26, M2 pxp = 0.44, M5 pxp = 0.30, bor = 0.775)  Note: Authors explicitly eschew p-values and report only bootstrapped 95% CIs. No Cohen's d, eta-squared, or other standardized effect sizes reported.
- **effect_size:** No standardized effect sizes (d, r-squared, eta-squared) reported for group comparisons; only raw Pearson r for correlations and bootstrapped CIs for mean differences.
- **learning_from:** Other (observed agent); agent's choice outcomes interpreted in context of agent's beliefs
- **learning_about:** Other (observed agent); agent's beliefs about program mode and intentions/preferences toward charities---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Modified Rescorla-Wagner with 2 learning rates: $\lambda_{Bel}$ (belief), $\lambda_{Int}$ (intent; attenuates over time as $\lambda_{Int}/t$). M1 — the a priori model.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "M1 (a priori: RW with attenuating intent LR)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BMS (protected exceedance probability)"} 2. {"name": "M2 (simple RW; no attenuation of intent LR)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BMS"} 3. {"name": "M3 (actual mode replaces belief estimates)", "family": "Rescorla-Wagner (modified)", "n_params": 1, "metric": "BMS"} 4. {"name": "M4 (actual mode for intent outcomes but not belief estimates)", "family": "Rescorla-Wagner (modified)", "n_params": 2, "metric": "BMS"} 5. {"name": "M5 (choice outcomes used directly, ignoring belief)", "family": "Rescorla-Wagner (modified)", "n_params": 2, "metric": "BMS"} 6. {"name": "M6 (belief fixed to normal for entire experiment)", "family": "Rescorla-Wagner (modified)", "n_params": 1, "metric": "BMS"} 7. {"name": "M7 (belief fixed to reversal for entire experiment)", "family": "Rescorla-Wagner (modified)", "n_params": 1, "metric": "BMS"}
- **model_mb_mf:** MEDIUM — classified as MF because core update is RW prediction error, but the belief-tracking component has model-based characteristics (tracking latent states). Could reasonably be classified as hybrid.
- **model_params:** - $\lambda_{Bel}$ (learning rate for belief about program mode; range [0, 1]): CTL1 mean = 0.49, CTL2 mean = 0.63, ASD mean = 0.56 - $\lambda_{Int}$ (learning rate for intent/charity preferences; range [0, 1]; attenuated by 1/t): CTL1 mean = 0.58, CTL2 mean = 0.48, ASD mean = 0.18 - [S] $\lambda_{Int}$ — this parameter governs learning about another person's intentions, which is inherently social
- **social_param:** $\lambda_{Int}$ [S] — learning rate for inferring the Agent's charitable intentions from observed choices, attenuated over time ($\lambda_{Int}/t$). This is the key social parameter; ASD participants had significantly lower $\lambda_{Int}$ than controls.
- **social_param_name:** $\lambda_{Int}$ [S]
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Bayesian model selection (BMS) — protected exceedance probability (pxp) and Bayesian omnibus risk (bor), implemented via hierarchical Bayesian fitting (mfit toolbox)
- **how_model_fit:** individual-level-fit (hierarchical Bayesian fitting with group priors estimated first, then individual learning rates estimated under those priors)
- **data_type_fit_to:** choice behavior (binary responses: belief, intent, and choice predictions on each trial)---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A — no neuroimaging
- **key_regions:** N/A — no neuroimaging
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A (no neuroimaging)---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 79 (53 CTL [split into CTL1 n=27, CTL2 n=26], 26 ASD); all high-functioning adults. CTL mean age = 31.6 (range 20–59); ASD mean age = 29.5 (range 20–59). 5 participants excluded (2 CTL, 3 ASD) for not performing task correctly.
- **population_category:** clinical
- **population_age_range:** 20–59
- **ecological_validity:** Low — artificial computer task with simulated agent choices (not real social interaction); authors explicitly note the task was "artificial and did not involve actual social interactions with people" and decomposed social cognition in a way not encountered in the real world. (HIGH — authors state this limitation directly)
- **eligibility_flag:** 
- **concerns:** - No standardized effect sizes reported (authors used only bootstrapped CIs and eschewed p-values); this limits comparability with other studies - Agent behavior was partially simulated (beliefs from real participants combined with simulated preferences), not fully naturalistic - ASD group heterogeneity: no single winning model for ASD (bor = 0.775), limiting interpretability - Small ASD sample (n = 26) limits power for individual-differences analyses and model comparison within ASD
- **limitations_reported:** Task was artificial and did not involve actual social interactions with people; task decomposed an aspect of social cognition not normally encountered as such in the real world; important for future work to design ecologically valid tasks that better mimic the real world; study limited to high-functioning adults with ASD necessitated by demands of the task; deficit could be further tested with simplified tasks in children and lower-functioning individuals; approximate time to complete experiment was ~2 hours making it challenging as a clinical instrument; within-ASD heterogeneity source remains an open question requiring longer tasks and test-retest validation
- **limitations_categorized:** Limited ecological validity; task simplicity/artificiality; limited generalizability (high-functioning adults only); sample size (small ASD group); task duration/clinical applicability; model heterogeneity in clinical group
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
- **wc_rule10:** Yes
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_autism
- pop_healthy_adults
- rr_pop_autism
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_mentalizing_inference
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_mod_mentalizing_inference
- tax_model_MB_MF_hybrid
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_primary_topic = mentalizing
- tax_rr_topic_mentalizing
- tax_topic_mentalizing
