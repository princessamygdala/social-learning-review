# Suzuki et al. (2015)

- **study_id:** `a84b2ae0f3b82710b_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Suzuki, S., Adachi, R., Dunne, S., Bossaerts, P., & O'Doherty, J. P. (2015). Neural mechanisms underlying human consensus decision-making. *Neuron*, *86*(2), 591–602. https://doi.org/10.1016/j.neuron.2015.03.019
- **citation_short:** Suzuki et al. (2015)
- **doi:** 10.1016/j.neuron.2015.03.019
- **publication_type:** peer-reviewed journal
- **year:** 2015.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DivisionoftheHumanitiesandSocialSciences,CaliforniaInstituteofTechnology,Pasadena,CA91125,USA; InstituteofNeuroscienceandMentalHealth,TheUniversityofMelbourne,Parkville,VIC3052,Australia; FacultyofBusinessandEconomics,TheUniversityofMelbourne,Carlton,VIC3010,Australia; SchoolofLetters,HokkaidoUniversity,Sapporo,Hokkaido060-0810,Japan; SchoolofBusiness,UniversityofUtah,SaltLakeCity,UT84112,USA; ethecomputationalmodelandexamineitsneuralun-; etheMRIscannerinteractswithotherparticipants; InstituteofTechnology,Pasadena,CA91125,USA; emails: shinsuke.szk@gmail.com
- **code_url:** 

## Computational level
- **study_focus:** Consensus decision-making / social influence learning — how individuals integrate own preferences with group members' prior choices and inferred "stickiness" (others' latent preferences) to reach unanimous group consensus.
- **study_focus_short:** Consensus decision-making / social influence learning
- **learning_mode_description:** - Learning mode: Learning from group members' choices about others' latent preferences (stickiness) to guide consensus decisions   - Learning from:     - Source type (social): group (other group members, 3–5 others)     - Source content (social): action/policy (others' observed choices across trials)   - Learning about:     - Target type (social): group (other group members' latent preferences)     - Target content (social): state (mental state; others' preference/stickiness for items)
- **task_description:** In groups of 4 or 6, participants repeatedly chose between two everyday items, viewing the distribution of others' choices after each trial, until unanimous consensus was reached or the block ended. Preferences for items were measured via BDM auction before and after the task.
- **task_paradigm:** Social influence task
- **players:** Multi-agent (group of 4 or 6), symmetric. Single agent scanned (participant), multi-target (3 or 5 other group members).
- **n_players:** small group (3-4)
- **partner_type:** human (live)
- **stimuli:** Everyday consumer items (pairs), red dots indicating others' choices.
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - Participants' choices guided by own preference, group members' prior choice, and estimated stickiness (full model best fit; BF > 150 vs. second-best model; p < 0.01, LRT)   - Correlation between stickiness decision weight and tendency to change behavior (r = 0.72, p < 0.01, partial correlation; r = 0.68, p < 0.01, zero-order)   - vmPFC correlated with preference for chosen item (p < 0.05, SVC)   - Right pSTS/TPJ correlated with group members' prior choice (p < 0.05, whole-brain corrected) — selectively in social condition (p < 0.05, SVC for main > control)   - Bilateral IPS correlated with estimated stickiness (p < 0.05, whole-brain corrected) — present in both social and control conditions   - dACC correlated with integrated choice probability (p < 0.05, whole-brain corrected) and showed PPI connectivity with vmPFC, pSTS/TPJ, and IPS
- **effect_size:** - Main Results:   - Participants' choices guided by own preference, group members' prior choice, and estimated stickiness (full model best fit; BF > 150 vs. second-best model; p < 0.01, LRT)   - Correlation between stickiness decision weight and tendency to change behavior (r = 0.72, p < 0.01, partial correlation; r = 0.68, p < 0.01, zero-order)   - vmPFC correlated with preference for chosen item (p < 0.05, SVC)   - Right pSTS/TPJ correlated with group members' prior choice (p < 0.05, whole-brain corrected) — selectively in social condition (p < 0.05, SVC for main > control)   - Bilateral IPS correlated with estimated stickiness (p < 0.05, whole-brain corrected) — present in both social and control conditions   - dACC correlated with integrated choice probability (p < 0.05, whole-brain corrected) and showed PPI connectivity with vmPFC, pSTS/TPJ, and IPS
- **learning_from:** Group (other group members); others' observed choices (distribution of choices across trials).
- **learning_about:** Group (other group members); others' latent preferences/stickiness for items (mental state inference).  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Bayesian learning of stickiness + weighted sum decision model (3 weights: w_preference, w_majority, w_stickiness; 1 inverse temperature beta)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** [   {"name": "Full model (preference + majority + stickiness)", "family": "Bayesian + weighted sum", "n_params": 4, "metric": "BIC"},   {"name": "Preference + majority", "family": "weighted sum", "n_params": 3, "metric": "BIC"},   {"name": "Preference + stickiness", "family": "Bayesian + weighted sum", "n_params": 3, "metric": "BIC"},   {"name": "Majority + stickiness", "family": "Bayesian + weighted sum", "n_params": 3, "metric": "BIC"},   {"name": "Preference only", "family": "weighted sum", "n_params": 2, "metric": "BIC"},   {"name": "Majority only", "family": "weighted sum", "n_params": 2, "metric": "BIC"},   {"name": "Stickiness only", "family": "Bayesian + weighted sum", "n_params": 2, "metric": "BIC"},   {"name": "Couzin et al. (2005) variant", "family": "weighted sum with modulated majority", "n_params": "not stated", "metric": "BIC"} ]
- **model_mb_mf:** MB (model-based — Bayesian inference about latent structure)
- **model_params:** - w_preference: decision weight for own preference [not S] - w_majority: decision weight for group members' prior choice [S] - w_stickiness: decision weight for estimated stickiness [S] - β (inverse temperature): softmax temperature - Note: Mean fitted values not reported in main text. Cross-correlations reported in Figure S3.
- **social_param:** w_majority — weight given to group members' prior choices; w_stickiness — weight given to inferred stickiness (others' latent preferences). The stickiness variable itself is a Bayesian-inferred hidden state reflecting others' preference strength.
- **social_param_name:** w_majority
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC; also Bayesian model selection (Stephan et al., 2009); likelihood ratio test (LRT)
- **how_model_fit:** individual-level-fit (hierarchical modeling approach for parameter estimation, with individual model fits also performed as robustness check)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) + PPI (psychophysiological interaction)
- **contrast:** - Preference for chosen item at decision onset → vmPFC (p < 0.05, SVC) - Group members' prior choice (% choosing participant's chosen item) at decision onset → right pSTS/TPJ (p < 0.05, whole-brain corrected; social-specific) - Estimated stickiness of chosen item at decision onset → bilateral IPS (p < 0.05, whole-brain corrected; domain-general) - Integrated choice probability at decision onset → dACC, rACC (p < 0.05, whole-brain corrected) - PPI: vmPFC-dACC connectivity at decision (p < 0.05); pSTS/TPJ-dACC connectivity at decision (p < 0.01); IPS-dACC connectivity at decision (p < 0.05)
- **key_regions:** Own preference value in vmPFC; group members' prior choice (social-specific) in right pSTS/TPJ; estimated stickiness (domain-general) in bilateral IPS; integration of all three signals in dACC; rACC also tracked choice probability but lacked connectivity with input regions.
- **key_regions_abbrev:** vmPFC, mPFC, dACC, ACC, TPJ, STS, AI
- **coordinates_peak:** unavailable — not in main text; coordinates reported in supplementary Tables S1 and S2 which are not accessible.
- **analysis_type:** both (whole-brain corrected analyses + independent ROI analyses with small-volume correction)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** Main experiment: N = 120 (20 scanned with fMRI, 100 not scanned). Control experiment: N = 20 (separate participants, all scanned). Total scanned: N = 40. Age/demographics not specified in main text.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Participants made real choices about everyday consumer items with real incentives (they could obtain chosen items). However, communication was limited to observing choice distributions (red dots) with no verbal or face-to-face interaction, reducing ecological validity compared to real group deliberation. Group sizes (4 and 6) are relatively small.
- **eligibility_flag:** 
- **concerns:** - MNI coordinates only in supplement (Tables S1, S2), which is not accessible — cannot verify exact peak locations. - Mean fitted parameter values not reported in main text; distributions in supplementary figures only. - The stickiness variable is an inference about others' preferences, but the Bayesian learning model is relatively simple (assumes others' choices generated by stickiness + prior majority choice). More complex theory-of-mind models were not tested. - Control experiment used different participants (between-subjects), which limits direct comparison power. - The paper refers to "consensus decision-making" but the learning component is specifically the trial-by-trial Bayesian updating of the stickiness estimate.
- **limitations_reported:** The authors note ambiguity in the precise physiological mechanism underlying repetition suppression in vmPFC; they acknowledge the study cannot completely exclude alternative accounts for decreased vmPFC activity (e.g., transition to habitual behavioral control); they note the need for future cross-species comparative studies; they note the study moves beyond dyadic paradigms but acknowledge the need for further work on larger group contexts.
- **limitations_categorized:** limited ecological validity; mechanistic ambiguity (repetition suppression interpretation); limited model complexity; between-subjects control design; limited generalizability (to larger/more naturalistic groups)
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
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - coordinates_peak: LOW — reported only in supplementary Tables S1/S2, not accessible - model_params (mean fitted values): LOW — reported only in supplementary figures - sample_size (demographics): MEDIUM — age range not specified in main text - all_models_tested (n_params for Couzin variant): LOW — not explicitly stated - wc_guidelines rule 3 (simulation): MEDIUM — may be in supplement but cannot verify
- **cannot_find:** - Exact MNI coordinates (in supplement Tables S1, S2 — not accessible) - Mean fitted parameter values (in supplementary figures — not accessible) - Exact model formula / equations (described graphically in Figure 3A; full mathematical specification in Supplemental Experimental Procedures — not accessible) - Age/demographic breakdown of participants
- **other_notes:** The study has both a main social experiment (interaction with real humans) and a control nonsocial experiment (interaction with computer algorithm). The key finding is a dissociation: vmPFC (preference) and IPS (stickiness) are domain-general, while pSTS/TPJ (group members' prior choice) is social-specific. dACC integrates all three signals via functional connectivity (PPI). The Bayesian stickiness inference is the core learning component — it updates trial-by-trial based on observed group choices. Supplement not accessible — model equations, parameter recovery, and MNI coordinates could not be verified.
- **re_extract_flag:** false (full text was accessible; however, supplement was not accessible, and coordinates + detailed model equations are in the supplement)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_mentalizing_inference
- rr_tax_mod_multiplayer_live
- rr_tax_mod_social_info_search
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_B_inference_modelling_others
- tax_mod_mentalizing_inference
- tax_mod_multiplayer_live
- tax_mod_social_info_search
- tax_model_MB
- tax_model_bayesian
- tax_param_perseveration
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_social_weight
- tax_rr_primary_topic = norm_conformity
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_mentalizing
- tax_rr_topic_norm_conformity
- tax_topic_mentalizing
- tax_topic_norm_conformity
