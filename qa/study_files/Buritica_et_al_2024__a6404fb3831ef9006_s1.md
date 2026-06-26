# Buritica et al. (2024)

- **study_id:** `a6404fb3831ef9006_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Rodriguez Buritica, J. M., Eppinger, B., Heekeren, H. R., Crone, E. A., & van Duijvenvoorde, A. C. K. (2024). Observational reinforcement learning in children and young adults. *npj Science of Learning*, *9*, 18. https://doi.org/10.1038/s41539-024-00227-9
- **citation_short:** Buritica et al. (2024)
- **doi:** 10.1038/s41539-024-00227-9
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofPsychology,EducationandChildStudies,ErasmusUniversityRotterdam,Rotterdam,Netherlands; ethoughtofasimportantlearningsignals,andareshowntoscalewith outcomesbeforemakingtheirownchoice; schoolsandothersocialenvironments,inwhichwehavethe encephalogram (EEG)9,10; DepartmentofEducationandPsychology,FreieUniversitätBerlin,Berlin,Germany; DepartmentofPsychology,TechnischeUniversitätDresden,Dresden,Germany; DepartmentofPsychology,UniversityofGreifswald,Greifswald,Germany; SchoolofMindandBrain&DepartmentofPsychology,HumboldtUniversityof; InstituteforBrainandCognition,Leiden,TheNetherlands; em
- **code_url:** 

## Computational level
- **study_focus:** Observational learning — developmental differences in neurocomputational mechanisms of learning from observing others' choices and outcomes versus learning from own outcomes in children (8–10 years) and young adults (18–20 years).
- **study_focus_short:** Observational learning
- **learning_mode_description:** - Learning mode: Learning from observing another agent's choices and reward outcomes to update one's own value representations for subsequent individual choice.     - Learning from:       - Source type (social): other (age-matched peer / model player)       - Source content (social): outcomes (reward/loss feedback of the observed other's choice)     - Learning about:       - Target type (non-social): world (stimulus–reward contingencies)       - Target content (non-social): stimulus (value of abstract choice options)
- **task_description:** Participants made repeated choices between pairs of abstract stimuli with probabilistic reward contingencies (80/20%) across an observational learning condition (where they first observed an age-matched peer's choice and outcome before choosing themselves) and an individual learning condition (no observation). The task was performed inside an fMRI scanner over three runs (48 trials per condition).
- **task_paradigm:** Observational learning task
- **players:** Single agent (participant), single observed other (age- and gender-matched peer, actually computer-generated)
- **n_players:** single agent (1)
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract visual stimuli (vector snowflakes), binary probabilistic reward feedback (gain/loss)
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:     - Both age groups performed above chance in both conditions; better performance in observational vs. individual learning (β = 0.12)     - Adults outperformed children across conditions (β = 0.10)     - Positive learning rates higher than negative learning rates across conditions (β = 0.75)     - Adults showed higher inverse temperature (more value-driven choices) than children (β = 0.91)     - Higher inverse temperature in observational vs. individual condition (β = 0.95)     - Individual > observational PE activation in bilateral caudate, vmPFC, bilateral parietal cortex, left lateral PFC (whole-brain FWE cluster-corrected)     - Age (adults > children) × condition (IL > OL) interaction in left TPJ/inferior parietal cortex (FWE cluster-corrected)     - Observational PEs: stronger activation in adults vs. children in dmPFC, dlPFC, right inferior parietal, right insula (FDR cluster-corrected)     - dmPFC observational PE activation correlated with observational learning performance across both age groups (β = −1.12; R² = .38)     - Brain-behavior: dlPFC observational PE ~ performance (R² = .28, did not survive FDR correction)     - Correlation between OL and IL performance (r = 0.46)     - Condition effect on accuracy (R² = .31 from full mixed model)
- **effect_size:** - Main Results:     - Both age groups performed above chance in both conditions; better performance in observational vs. individual learning (β = 0.12)     - Adults outperformed children across conditions (β = 0.10)     - Positive learning rates higher than negative learning rates across conditions (β = 0.75)     - Adults showed higher inverse temperature (more value-driven choices) than children (β = 0.91)     - Higher inverse temperature in observational vs. individual condition (β = 0.95)     - Individual > observational PE activation in bilateral caudate, vmPFC, bilateral parietal cortex, left lateral PFC (whole-brain FWE cluster-corrected)     - Age (adults > children) × condition (IL > OL) interaction in left TPJ/inferior parietal cortex (FWE cluster-corrected)     - Observational PEs: stronger activation in adults vs. children in dmPFC, dlPFC, right inferior parietal, right insula (FDR cluster-corrected)     - dmPFC observational PE activation correlated with observational learning performance across both age groups (β = −1.12; R² = .38)     - Brain-behavior: dlPFC observational PE ~ performance (R² = .28, did not survive FDR correction)     - Correlation between OL and IL performance (r = 0.46)     - Condition effect on accuracy (R² = .31 from full mixed model)
- **learning_from:** other (age-matched peer); observed choices and reward outcomes of the other player
- **learning_about:** world; stimulus–reward contingencies (value of abstract choice options)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Dual-update Q-learning with two valence-specific learning rates (α_pos, α_neg) and inverse temperature (β), applied separately in observational (OL PN) and individual (IL PN) conditions. Q_a(t+1) = Q_a(t) + α[r(t) − Q_a(t)] with dual update for chosen and unchosen options; softmax: P(a) = exp(Q_a × β) / [exp(Q_a × β) + exp(Q_b × β)]
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** - {"name": "IL Base (single α, β)", "family": "Q-learning", "n_params": 2, "metric": "BIC"}   - {"name": "IL PN (α_pos, α_neg, β)", "family": "Q-learning", "n_params": 3, "metric": "BIC"}   - {"name": "OL Base (single α, β; dual-update)", "family": "Q-learning", "n_params": 2, "metric": "BIC"}   - {"name": "OL PN (α_pos, α_neg, β; dual-update)", "family": "Q-learning", "n_params": 3, "metric": "BIC"}   - {"name": "OL OA (α_other, α_own, β; dual-update)", "family": "Q-learning", "n_params": 3, "metric": "BIC"}
- **model_mb_mf:** MF
- **model_params:** - α_pos: positive learning rate; median adults IL ~0.78 (from group-level description); constrained [0,1]   - α_neg: negative learning rate; median ~0.2 (from group-level description); constrained [0,1]   - β: inverse temperature; median OL = 2.14, median IL = 1.03, adults median = 2.18, children median = 1.13; constrained [0,5]   - Note: In OL condition, the model applies dual-update (observational stage + action stage) with the same α_pos/α_neg parameters [S — the dual-update structure (observational stage Eq. 4) is the social component]
- **social_param:** The dual-update structure itself (observational stage update, Eq. 4: Q_a(t+1) = Q_a(t) + α[r_Other(t) − Q_a(t)]) is the social mechanism — values are updated from the observed other's outcomes. No separate named social parameter; the social element is architectural (dual-update from other's outcomes) rather than a distinct parameter. In the OL OA model (not winning), α_other [S] was an explicit social learning rate for the observational stage.
- **social_param_name:** The dual-update structure itself
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (Bayesian Information Criterion); summed across all participants. Best model (PN) had lower BIC than second-best by 192 (IL condition) and 313 (OL condition).
- **how_model_fit:** individual-level-fit (L-BFGS-B optimization via optim in R; starting values set to 0.5 per parameter per age group)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — trial-level PEs from the RL model entered as parametric modulators of outcome regressors in a GLM
- **contrast:** - Individual PE > Observational PE (whole-brain FWE cluster p < .05): bilateral caudate, vmPFC, left lateral PFC, bilateral parietal cortex   - Age (adults > children) × condition (IL > OL) interaction: left TPJ/inferior parietal cortex   - Observational PE activation (F-test): right angular gyrus, right lateral PFC/IFG, right SMA, right insula   - Individual PE activation (F-test): vmPFC, bilateral striatum, left occipital cortex   - Age differences in observational PEs (adults > children): dmPFC, bilateral dlPFC, bilateral inferior parietal cortex, precuneus, right insula   - Brain-behavior: dmPFC observational PE ~ observational learning accuracy (survived FDR correction)
- **key_regions:** Observational PE coding in dmPFC (stronger in adults, correlated with learning performance across ages); individual PE in ventral striatum and vmPFC; age × condition interaction in left TPJ/inferior parietal; observational PE age differences in dlPFC, parietal cortex, insula, precuneus.
- **key_regions_abbrev:** VS, striatum, vmPFC, mPFC, dmPFC, dlPFC, TPJ, insula, precuneus, parietal
- **coordinates_peak:** - *Individual > Observational PE (Supp Table 4):*     - Right Caudate: 15, 17, 4     - Left Caudate: -15, 20, -5     - Right Angular Gyrus: 60, -55, 28     - Right Inferior Parietal Lobule: 60, -52, 43     - Left Inferior Parietal Lobule: -51, -55, 46     - Left Frontal Inferior Triangularis: -48, 41, 7     - Left Medial Superior Frontal Gyrus: -9, 65, 4     - Left Anterior Cingulum: -3, 50, 1   - *Age (adults > children) × condition (IL > OL) (Supp Table 5):*     - Left Inferior Parietal Lobule (TPJ): -48, -40, 37     - Left Supramarginal Gyrus: -54, -49, 28     - Right Middle Occipital Gyrus: 27, -73, 31   - *Observational PE — F-test (Supp Table 6):*     - Right Angular Gyrus: 57, -55, 37     - Right Frontal Inferior Operculum: 39, 17, 34     - Right Middle Frontal Gyrus: 45, 20, 40     - Right SMA: 3, 20, 46     - Right Insula: 33, 20, -2   - *Individual PE — F-test (Supp Table 7):*     - Left Medial Superior Frontal Gyrus (vmPFC): -6, 65, 1     - Right Orbital Medial Frontal Gyrus: 0, 53, -2     - Left Middle Occipital Gyrus: -45, -70, 25     - Left Olfactory Bulb: -15, 8, -14     - Left Inferior Temporal Gyrus: -57, -52, -11     - Right Caudate: 9, 14, -8   - *Age differences in observational PE (adults > children; Supp Table 8):*     - Left Precuneus: -9, -76, 43     - Right Precuneus: 3, -57, 55     - Left Inferior Parietal Lobe: -48, -49, 49     - Right Inferior Parietal Lobe: 42, -40, 37     - Right Inferior Frontal Gyrus (dlPFC): 42, 14, 34     - Left Middle Frontal Gyrus (dlPFC): -42, 17, 43     - Left Superior Medial Gyrus (dmPFC): 0, 26, 43
- **analysis_type:** whole-brain (with ROI extraction for brain-behavior analyses from whole-brain identified clusters)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 59 (30 adults, age M = 19.45, SD = 0.86, 16 female; 29 children after exclusion, age M = 9.71, SD = 0.89, 18 female). One child excluded for not completing the task; 5 participants had one run excluded for motion.
- **population_category:** mixed
- **population_age_range:** M=19.45 (SD=0.86)
- **ecological_validity:** Moderate-to-low. Lab-based fMRI paradigm with abstract stimuli and a fictitious "peer" whose choices were actually computer-generated. The observational learning manipulation was ecologically motivated (learning from peers) but the social context was simulated. Participants believed the other player was real and rated them as credible (93% reported paying attention).
- **eligibility_flag:** 
- **concerns:** - The "social agent" is a computer-generated model player, not a real person (though participants believed it was real)   - Children had significantly higher age-normed IQ than adults (η²_p = 0.08); IQ was controlled for but this is unusual   - The winning model (IL PN) fit children's data slightly worse than the baseline (IL Base) model (BIC difference of 14 in favor of Base for children in IL condition), but PN was selected as best across all participants   - The dual-update model does not include an explicit social parameter — the social element is structural (observational stage update)   - Median parameter estimates per age group were used for fMRI PE regressors rather than individual-level estimates   - No explicit social vs. non-social comparison condition (the IL condition removes observation but also reduces information)
- **limitations_reported:** It is important to compare active individual learning to observational learning, where participants learn purely passively from observed information"; "an important question is to what extent findings are specific to social learning or reflective of more general learning processes"; "our age groups differed in fluid intelligence. Children showed higher age-normed intelligence scores than adults, which may have influenced age-related differences in performance and neural activation"; "in contrast to previous findings on observational learning, we did not find age-related performance differences between learning conditions"; "differences to results of previous studies arise because of the administered paradigm to make the task amenable for fMRI"; "with the current task design, stochasticity and exploration cannot be easily distinguished
- **limitations_categorized:** limited ecological validity; confound between social information and information quantity; IQ group differences; task simplicity (adapted for fMRI); cannot distinguish exploration from stochasticity; cross-sectional design (two age groups only)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 10
- **wc_total:** 10.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `model_params` (MEDIUM): Exact mean fitted values per parameter per age group and condition are described only as medians in the text (e.g., "median = 0.78 for positive LR", "median = 0.2 for negative LR"); full parameter distributions shown in figures but not tabled numerically   - `social_param` (MEDIUM): No explicit social parameter in the winning model; social element is architectural (dual-update from other's outcomes). The OL OA model (non-winning) had α_other as explicit social parameter.   - `learning_about` target classification (MEDIUM): Classified as non-social (world/stimulus values) because participants are learning stimulus-reward contingencies, though the information source is social
- **cannot_find:** - Exact mean (not median) parameter values per cell (age group × condition × parameter) — shown in box plots (Supplementary Fig. 5) but not tabled   - Preregistration status not mentioned
- **other_notes:** - This paper has a strong developmental focus (children vs. adults) which is the primary contribution   - The Wilson & Collins checklist is unusually well-satisfied: model recovery, parameter recovery, and posterior predictive checks are all reported   - Data and code are publicly available in the Leiden Repository (https://doi.org/10.34894/W4WMPZ)   - The "other player" was described as an age- and gender-matched peer met before the experiment, but choices were actually computer-generated using an RL model (revealed in supplement)
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_children
- pop_healthy_adults
- rr_pop_children
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = dedicated
- spec_source = social
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_param_social_bonus
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_PE_signal
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = imitation_emulation
- tax_rr_topic_imitation_emulation
- tax_topic_imitation_emulation
