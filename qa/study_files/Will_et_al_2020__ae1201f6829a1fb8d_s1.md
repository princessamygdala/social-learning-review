# Will et al. (2020)

- **study_id:** `ae1201f6829a1fb8d_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Will, G.-J., Moutoussis, M., Womack, P. M., Bullmore, E. T., Goodyer, I. M., Fonagy, P., Jones, P. B., NSPN Consortium, Rutledge, R. B., & Dolan, R. J. (2020). Neurocomputational mechanisms underpinning aberrant social learning in young adults with low self-esteem. *Translational Psychiatry*, *10*, 96. https://doi.org/10.1038/s41398-020-0702-4
- **citation_short:** Will et al. (2020)
- **doi:** 10.1038/s41398-020-0702-4
- **publication_type:** peer-reviewed journal
- **year:** 2020.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** CentreforHumanNeuroimaging,UniversityCollegeLondon, we use computational modeling and functional magnetic; UniversityCollegeLondonCentreforComputationalPsychiatry includingdepression6,7,anxiety2,8andpsychosis9,10; mittedbystatutoryregulationorexceedsthepermitteduse,youwillneedtoobtain; mitsuse,sharing,adaptation,distributionandreproduction; lableattheendofthearticle; etherotherpeoplelikedthem; emails: gjwill@gmail.com
- **code_url:** 

## Computational level
- **study_focus:** Social approval learning / self-esteem updating — how low self-esteem biases learning from social approval prediction errors, affecting both expectations about being liked ("reflected self-appraisals") and momentary feelings of self-worth ("direct self-appraisals").
- **study_focus_short:** Social approval learning / self-esteem updating
- **learning_mode_description:** - Learning mode: Learning from social approval/disapproval feedback about one's own social standing and self-worth   - Learning from:     - Source type (social): other (184 peer raters, organized into 4 groups)     - Source content (social): outcome (approval / disapproval feedback)   - Learning about:     - Target type (social): self (own social value / self-worth)       - If joint: not joint     - Target content (social): state (mental state; self-esteem / self-worth) AND outcome (expected social value — probability of being liked)
- **task_description:** Participants predicted whether each of 184 peer raters (sorted into 4 groups by approval propensity: 87%, 67%, 33%, 13%) would like them based on their online character profile, then received algorithmic approval/disapproval feedback; after every 2–3 trials they reported momentary self-worth on a visual analog scale.
- **task_paradigm:** Self-evaluation / self-esteem task
- **players:** Single agent (participant), multi-target (184 raters; 4 groups by approval rate)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Names + color-coded group cues for raters, thumbs-up/thumbs-down feedback symbols, visual analog self-worth scale
- **method:** fMRI
- **method_full:** fMRI (model-based)
- **main_result:** - Main Results:   - Low SE participants predicted being liked less often than high SE (B = 0.22, SE = 0.09, χ²(1) = 5.47)   - Low SE had lower initial expected social value than high SE (Mann-Whitney z = −2.29)   - Low SE had lower learning rates for SPEs (Mann-Whitney z = −2.30)   - Low SE had lower baseline self-worth parameter w₀ (Mann-Whitney z = −3.45)   - Global self-esteem positively associated with w₀ (ρ = 0.60)   - Global self-esteem negatively associated with w₁ (ρ = −0.36)   - CCA: single canonical dimension of "interpersonal vulnerability" (canonical r = 0.79)   - Interpersonal vulnerability modulated ESV-related vmPFC activity (peak: −2, 59, −11; k = 687; FWE cluster-corrected)   - Self-worth updates tracked in vmPFC (peak: −3, 47, −11; t(60) = 4.37, k = 584, FWE cluster-corrected)   - Self-worth updates tracked in dPFC/BA 8m (peak: −23, 29, 51; t(60) = 5.95, k = 2896, FWE cluster-corrected)   - dPFC updating activity correlated with interpersonal vulnerability (ρ = 0.25)   - SPE correlated with VS/sgACC activity in independent ROI (z = 2.95)   - No group difference in SPE neural signal in VS/sgACC (z = −0.65)   - Main effect of self-esteem on self-worth ratings (ηp² = 0.22)   - Main effect of social feedback on self-worth ratings (ηp² = 0.38)
- **effect_size:** - Main Results:   - Low SE participants predicted being liked less often than high SE (B = 0.22, SE = 0.09, χ²(1) = 5.47)   - Low SE had lower initial expected social value than high SE (Mann-Whitney z = −2.29)   - Low SE had lower learning rates for SPEs (Mann-Whitney z = −2.30)   - Low SE had lower baseline self-worth parameter w₀ (Mann-Whitney z = −3.45)   - Global self-esteem positively associated with w₀ (ρ = 0.60)   - Global self-esteem negatively associated with w₁ (ρ = −0.36)   - CCA: single canonical dimension of "interpersonal vulnerability" (canonical r = 0.79)   - Interpersonal vulnerability modulated ESV-related vmPFC activity (peak: −2, 59, −11; k = 687; FWE cluster-corrected)   - Self-worth updates tracked in vmPFC (peak: −3, 47, −11; t(60) = 4.37, k = 584, FWE cluster-corrected)   - Self-worth updates tracked in dPFC/BA 8m (peak: −23, 29, 51; t(60) = 5.95, k = 2896, FWE cluster-corrected)   - dPFC updating activity correlated with interpersonal vulnerability (ρ = 0.25)   - SPE correlated with VS/sgACC activity in independent ROI (z = 2.95)   - No group difference in SPE neural signal in VS/sgACC (z = −0.65)   - Main effect of self-esteem on self-worth ratings (ηp² = 0.22)   - Main effect of social feedback on self-worth ratings (ηp² = 0.38)
- **learning_from:** Other (peer raters); social approval/disapproval feedback (thumbs up/down)
- **learning_about:** Self; own social value (expected probability of being liked) and momentary self-worth  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** RW learning model for choices + exponential kernel regression for self-worth (9 params: η, ESV₀_high, ESV₀_low, T, ESV₀_bias, w₀, w₁, γ, σ)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "Model 1: Learning and positive bias", "family": "RW + kernel regression", "n_params": 9, "metric": "BIC (summed) = −1693"} 2. {"name": "Model 2: Learning, but no bias", "family": "RW + kernel regression", "n_params": 8, "metric": "BIC = −909 (ΔBIC = +428)"} 3. {"name": "Model 3: Correct initial beliefs about approval", "family": "Kernel regression (no learning)", "n_params": 6, "metric": "BIC = −1646 (ΔBIC = +47)"} 4. {"name": "Model 4: Separate term for expectations", "family": "RW + kernel regression", "n_params": 10, "metric": "BIC = −1130 (ΔBIC = +563)"} 5. {"name": "Model 5: Free initial beliefs about approval (self-worth only)", "family": "Kernel regression", "n_params": 6, "metric": "BIC = −9602"} 6. {"name": "Model 6: Outcome valence only (self-worth only)", "family": "Kernel regression", "n_params": 4, "metric": "BIC = −9274 (ΔBIC = +328 vs Model 5)"}
- **model_mb_mf:** MF
- **model_params:** - η (learning rate) [S]: weight given to SPEs in updating expected social value. Median fitted: 0.01 (low SE), 0.05 (high SE). Range: 1×10⁻⁵ to 1. - ESV₀_high (initial expected approval rate, most positive group) [S]: free parameter for initial expected social value for 87% group - ESV₀_low (initial expected approval rate, least positive group) [S]: free parameter for initial expected social value for 13% group - T (decision temperature): softmax temperature transforming ESV into choice probabilities - ESV₀ (response bias) [S]: value of predicting being liked over and above estimated ESV - w₀ (baseline self-worth) [S]: baseline component of self-worth constant throughout task. Correlated with global SE (ρ = 0.60) - w₁ (weight of SPEs on self-worth) [S]: extent to which momentary self-worth is shaped by SPEs. Correlated with global SE (ρ = −0.36) - γ (forgetting factor): decay of influence of past prediction errors on self-worth (0 ≤ γ ≤ 1) - σ (noise): measurement noise in self-worth equation
- **social_param:** - η (learning rate): rate of updating expected social value in response to social approval prediction errors; lower in low SE participants - w₁ (weight of SPEs on self-worth): degree to which social prediction errors determine momentary self-worth; higher (more negative) in low SE participants - ESV₀ (response bias): propensity to predict being liked beyond learned expected social value
- **social_param_name:** η
- **social_param_value:** 0.01
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (summed across participants); lower BIC preferred
- **how_model_fit:** individual-level-fit (maximum log-likelihood with flat priors, fitted to individual subjects' behavioral data)
- **data_type_fit_to:** choice behavior (predictions about being liked) + self-report ratings (momentary self-worth)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors derived from computational model: ESV at cue onset, SPE at feedback, self-worth updates at feedback)
- **contrast:** - ESV as parametric modulator at cue onset (interaction with interpersonal vulnerability → vmPFC cluster) - SPE as parametric modulator at feedback onset (replication of VS/sgACC signal in independent ROI) - Self-worth update as parametric modulator at feedback onset (whole-brain → vmPFC and dPFC clusters) - Group comparison (high vs low SE) on SPE-related activity in VS/sgACC ROI (no significant difference)
- **key_regions:** Expected social value modulated by interpersonal vulnerability in anterior vmPFC; social prediction errors in VS/sgACC (replicated from prior study); self-worth updates in vmPFC and left dorsal PFC (BA 8m); dPFC updating-related activity correlated with interpersonal vulnerability.
- **key_regions_abbrev:** vmPFC, mPFC, ACC, sgACC
- **coordinates_peak:** - vmPFC (ESV × interpersonal vulnerability): −2, 59, −11 - vmPFC (self-worth updates): −3, 47, −11 - dPFC / BA 8m (self-worth updates): −23, 29, 51 - VS/sgACC (SPE, independent ROI from prior study): 5, 20, −8
- **analysis_type:** both (whole-brain FWE cluster-corrected analyses + independent ROI analyses using 6-mm spheres from prior study)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 61 (30 low self-esteem, 31 high self-esteem); ages 18–30 (mean ~21); 34 females; drawn from bottom/top decile of RSES in NSPN 2400 cohort (n = 2,402). Control "other evaluation" task: same N = 61.
- **population_category:** healthy adults
- **population_age_range:** 18–30
- **ecological_validity:** Moderate. Participants created real online profiles about themselves, believed peer raters evaluated them, and reported genuine momentary self-worth. However, feedback was algorithmically generated (not real peer evaluations). Dictator Game donations toward raters resembled real prosocial behavior. Participants matched for age/gender but not for comorbid symptoms (depression, anxiety) — this was intentional to preserve ecological validity of self-esteem's natural comorbidity structure.
- **eligibility_flag:** 
- **concerns:** - Feedback was algorithmically generated, not from real peers (1 high SE, 1 low SE participant raised doubts about cover story) - dPFC correlation with interpersonal vulnerability (ρ = 0.25) was marginal and not robust to exclusion of participants who doubted cover story; authors acknowledge this needs replication - Self-esteem recruitment scores collected on average 27.6 months before scanning (range 12–52 months), though correlated with day-of-scanning scores (ρ = 0.74) - Low and high SE groups not matched on depression/anxiety symptoms — group differences could partly reflect comorbid psychopathology rather than self-esteem per se - No parameter recovery or model recovery reported - Code available "upon request" only (not openly shared)
- **limitations_reported:** Neural differences between groups may have been too small to detect within a sample size of 61 participants"; "findings allow limited claims about the specificity of self-esteem to the mechanisms identified"; "we had no a priori hypothesis about this region [dPFC] and that the effect was not robust to excluding participants from our analyses who reported doubts about the cover story, this result should be interpreted with caution and needs replication in larger samples
- **limitations_categorized:** sample size; limited specificity of self-esteem construct; robustness of dPFC finding; need for replication
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 7.0
- **wc_total:** 7.0

## Context flags
- **ctx_copresence:** unclear
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - effect_size: MEDIUM — many effect sizes reported as z-statistics from Mann-Whitney tests and Spearman ρ; some standardized effect sizes (ηp²) for ANOVAs; Cohen's d not reported for key group comparisons - model_params mean fitted values: MEDIUM — only median learning rates reported for the two groups (0.01 low SE, 0.05 high SE); mean fitted values for other parameters not explicitly reported - dPFC finding: LOW — marginal correlation (ρ = 0.25), not robust to participant exclusion; authors flag need for replication
- **cannot_find:** - Exact mean fitted values for all 9 parameters (only median learning rate and qualitative descriptions provided) - Exact formulas for Models 4, 5, 6 (partial equations given in supplement but text extraction is imperfect) - Preregistration status (not mentioned)
- **other_notes:** - This paper extends Will et al. (2017, eLife) using the same task paradigm but with extreme-group sampling (bottom/top 10% self-esteem). The 2017 paper used a general population sample (n = 40). - Control "other evaluation" task confirmed that learning differences were specific to self-evaluation, not general social learning impairments. - Dictator Game data showed prosocial behavior modulated by feedback but no self-esteem group differences. - CCA identified a single "interpersonal vulnerability" dimension linking computational parameters to psychiatric symptoms.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_anxiety
- pop_depression
- pop_healthy_adults
- rr_pop_anxiety
- rr_pop_depression
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
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_clinical
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
