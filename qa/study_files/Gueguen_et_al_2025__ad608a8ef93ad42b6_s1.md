# Gueguen et al. (2025)

- **study_id:** `ad608a8ef93ad42b6_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Gueguen, M., Cutler, J., Drew, D., Apps, M. A. J., Jeyaretna, D. S., Husain, M., Manohar, S. G., & Lockwood, P. L. (2025). Ventromedial prefrontal cortex lesions disrupt learning to reward others. *Brain*, Advance online publication. https://doi.org/10.1093/brain/awaf056
- **citation_short:** Gueguen et al. (2025)
- **doi:** 10.1093/brain/awaf056
- **publication_type:** peer-reviewed journal
- **year:** 2025.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Department of Experimental Psychology, University of Oxford, Anna Watts Building, Radcliffe; Centre for Human Brain Health, School of Psychology, UnivSersity of Birmingham, Edgbaston,; Centre for Human Brain Health, School of Psychology, University of Birmingham, Edgbaston,; Institute for Mental Health, School of Psychology, University of Birmingham, Edgbaston,; Department of Clinical Neurosciences, University of Oxford, Level 6, West Wing, John; Centre for Integrative N euroimaging, University of Oxford, FMRIB Building, John; Department of Neurology, John Radcliffe Hospital, Oxford, OX3 9DU,
- **code_url:** 

## Computational level
- **study_focus:** Prosocial reinforcement learning; the causal role of vmPFC and its subregions (sgACC, ACCg) in learning to reward others versus self versus no one.
- **study_focus_short:** Prosocial reinforcement learning
- **learning_mode_description:** - Learning mode: Learning from reward outcomes (points) about which abstract symbol maximises rewards for different recipients (self, other, no one).   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (reward/no reward feedback on chosen symbol)   - Learning about:     - Target type (social): other (anonymous participant) [in prosocial condition]     - Target type (non-social): self [in self condition]     - Target type (non-social): world [in no one/control condition]     - Target content (social/non-social): action/policy (which symbol to choose to maximise reward for each recipient)
- **task_description:** Participants completed a probabilistic reinforcement learning task choosing between two abstract symbols (75% vs 25% reward probability) across three interleaved recipient conditions: self (bonus for participant), other (bonus for anonymous other), and no one (control; points not converted to money). There were 144 trials total (48 per condition) with binary feedback (0 or 100 points).
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), single-target per condition (self / anonymous other / no one); confederate posed as other participant.
- **n_players:** single agent (1)
- **partner_type:** confederate
- **stimuli:** Abstract symbols (Agathodaimon font letters), binary point feedback (0 or 100 points), recipient cue text.
- **method:** lesion / behavioural
- **method_full:** Behavioural (lesion study with VLSM)
- **main_result:** - Main Results:   - vmPFC patients less accurate for other vs. no one (OR = 0.78, SE = 0.07, Z = -2.89, FDR p = 0.017)   - Group x recipient interaction (other vs. no one): vmPFC vs. HC (OR = 0.76 [0.63, 0.91], Z = -2.91); vmPFC vs. LC (OR = 0.67 [0.52, 0.86], Z = -3.13)   - vmPFC patients lost self-benefitting advantage: self vs. no one accuracy (OR = 0.96, BF01 = 3.61, substantial evidence for null)   - vmPFC patients had lower positive PE learning rates for other vs. no one compared to HC (OR = 0.84 [0.78, 0.91], Z = -4.36) and LC (OR = 0.87 [0.78, 0.97], Z = -2.58)   - vmPFC patients had higher negative PE learning rates for other vs. self compared to HC (OR = 1.06 [1.00, 1.12], Z = 2.11) and LC (OR = 1.13 [1.05, 1.22], Z = 3.16)   - VLSM: sgACC damage (area s24) associated with decreased other-no one positive PE LR difference (peak: +/-4, 20, -4; p = 0.005)   - VLSM: sgACC + ACCg damage associated with other-self negative PE LR difference (ACCg areas 24a'/b'; peak: +/-2, 34, 8; p = 0.017)
- **effect_size:** - Main Results:   - vmPFC patients less accurate for other vs. no one (OR = 0.78, SE = 0.07, Z = -2.89, FDR p = 0.017)   - Group x recipient interaction (other vs. no one): vmPFC vs. HC (OR = 0.76 [0.63, 0.91], Z = -2.91); vmPFC vs. LC (OR = 0.67 [0.52, 0.86], Z = -3.13)   - vmPFC patients lost self-benefitting advantage: self vs. no one accuracy (OR = 0.96, BF01 = 3.61, substantial evidence for null)   - vmPFC patients had lower positive PE learning rates for other vs. no one compared to HC (OR = 0.84 [0.78, 0.91], Z = -4.36) and LC (OR = 0.87 [0.78, 0.97], Z = -2.58)   - vmPFC patients had higher negative PE learning rates for other vs. self compared to HC (OR = 1.06 [1.00, 1.12], Z = 2.11) and LC (OR = 1.13 [1.05, 1.22], Z = 3.16)   - VLSM: sgACC damage (area s24) associated with decreased other-no one positive PE LR difference (peak: +/-4, 20, -4; p = 0.005)   - VLSM: sgACC + ACCg damage associated with other-self negative PE LR difference (ACCg areas 24a'/b'; peak: +/-2, 34, 8; p = 0.017)
- **learning_from:** Self; own reward outcomes (points) on chosen symbol in each recipient condition.
- **learning_about:** Other (anonymous participant) in prosocial condition; self in self condition; world (no one) in control condition — specifically, which action/symbol maximises reward for each recipient.  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Rescorla-Wagner with 6 learning rates (separate alpha_positive_PE and alpha_negative_PE for each of 3 recipients: self, other, no one) and 1 beta (6alpha1beta). Q(t+1)(s) = Q(t)(s) + alpha_[valence][recipient] x PE(t); PE(t) = r(t) - Q(t)(s); softmax with single beta.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "1alpha1beta", "family": "RW", "n_params": 2, "metric": "LME/BICint/exceedance probability"} 2. {"name": "3alpha1beta", "family": "RW", "n_params": 4, "metric": "LME/BICint/exceedance probability"} 3. {"name": "2alpha(S/O+N)1beta", "family": "RW", "n_params": 3, "metric": "LME/BICint/exceedance probability"} 4. {"name": "2alpha(O/S+N)1beta", "family": "RW", "n_params": 3, "metric": "LME/BICint/exceedance probability"} 5. {"name": "2alpha(N/S+O)1beta", "family": "RW", "n_params": 3, "metric": "LME/BICint/exceedance probability"} 6. {"name": "3alpha3beta", "family": "RW", "n_params": 6, "metric": "LME/BICint/exceedance probability"} 7. {"name": "0alpha1beta (WSLS)", "family": "Win-stay/lose-shift", "n_params": 1, "metric": "LME/BICint/exceedance probability"} 8. {"name": "0alpha3beta (WSLS)", "family": "Win-stay/lose-shift", "n_params": 3, "metric": "LME/BICint/exceedance probability"} 9. {"name": "6alpha_PE_1beta (WINNER)", "family": "RW (valence-split)", "n_params": 7, "metric": "LME/BICint/exceedance probability"} 10. {"name": "6alpha_PE_3beta", "family": "RW (valence-split)", "n_params": 9, "metric": "LME/BICint/exceedance probability"} 11. {"name": "4alpha_chosen_1beta", "family": "RW (chosen/unchosen)", "n_params": 5, "metric": "LME/BICint/exceedance probability"} 12. {"name": "5alpha_chosen_1beta", "family": "RW (chosen/unchosen)", "n_params": 6, "metric": "LME/BICint/exceedance probability"} 13. {"name": "6alpha_chosen_3beta", "family": "RW (chosen/unchosen)", "n_params": 9, "metric": "LME/BICint/exceedance probability"}
- **model_mb_mf:** MF
- **model_params:** - alpha_self_positive_PE [S]: learning rate for positive PEs, self condition - alpha_self_negative_PE [S]: learning rate for negative PEs, self condition - alpha_other_positive_PE [S]: learning rate for positive PEs, other condition - alpha_other_negative_PE [S]: learning rate for negative PEs, other condition - alpha_no_one_positive_PE: learning rate for positive PEs, no one condition - alpha_no_one_negative_PE: learning rate for negative PEs, no one condition - beta: temperature/decision noise parameter (single for all conditions) (Mean fitted values not reported in text or supplement.)
- **social_param:** alpha_other_positive_PE [S] and alpha_other_negative_PE [S] — learning rates for positive and negative prediction errors specifically when learning to benefit another person. These are the parameters that differentiate prosocial from self-benefitting learning.
- **social_param_name:** alpha_self_positive_PE
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Log Model Evidence (LME), exceedance probability (random-effects BMS), integrated BIC (BICint).
- **how_model_fit:** Individual-level fit (iterative MAP/expectation-maximisation, run separately per group).
- **data_type_fit_to:** Choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (lesion study with VLSM — voxel-based lesion-symptom mapping using permutation-based TFCE in FSL)
- **contrast:** - Positive PE learning rates: other - no one (sgACC, area s24) - Positive PE learning rates: other - self (sgACC + lateral vmPFC, area 13) - Positive PE learning rates: self - no one (lateral vmPFC, area 13) - Negative PE learning rates: other - self (ACCg areas 24a'/b' + sgACC areas s24/25) - Negative PE learning rates: self - no one (area 14c)
- **key_regions:** Prosocial positive PE learning in sgACC (area s24); prosocial negative PE learning in ACCg (areas 24a'/b') and sgACC (areas s24/25); self-benefitting advantage in lateral vmPFC (area 13); self-no one negative PE in area 14c.
- **key_regions_abbrev:** vmPFC, mPFC, ACC, sgACC
- **coordinates_peak:** - Positive PE, Other - No one (sgACC): +/-4, 20, -4 - Positive PE, Other - Self (vmPFC/sgACC): 8, 32, -20 - Positive PE, Self - No one (lateral vmPFC area 13): 8, 26, -12 - Negative PE, Other - Self: 8, 6, -16 - Negative PE, Other - Self: +/-4, 10, -10 - Negative PE, Other - Self (ACCg): +/-2, 34, 8 - Negative PE, Self - No one (area 14c): +/-8, 14, -22
- **analysis_type:** whole-brain (permutation-based VLSM with TFCE across all voxels with >= 5 patients damaged, Bonferroni corrected)  ---  ## QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 173 (28 vmPFC lesion patients, ages 37-76, mean = 57, 15 females; 21 lesion controls, ages 28-74, mean = 56, 13 females; 124 healthy controls, ages 20-80, mean = 53, 71 females). Groups matched on age, gender, empathy; vmPFC group matched to both controls on cognitive ability and apathy.
- **population_category:** mixed
- **population_age_range:** 37–76
- **ecological_validity:** Laboratory-based task with abstract symbols and binary feedback; deception procedure used to create belief in anonymous other participant (confederate); ecological validity limited by abstract stimuli and lack of real social interaction, though the monetary incentive structure and role-assignment procedure enhance motivational realism.
- **eligibility_flag:** 
- **concerns:** - Mean fitted parameter values not reported (only group comparisons of parameters) - Lesion patients have natural lesions with correlated voxel damage patterns, potentially biasing localization - No one condition interpreted as "non-social control" but could also index hypothetical vs. real reward distinction - Lesion maps were mirrored (no laterality hypothesis), which precludes detection of lateralized effects - VLSM restricted mostly to vmPFC due to voxel inclusion threshold (>= 5 patients), limiting detection of subcortical contributions
- **limitations_reported:** Both social behaviours and reinforcement learning rely on large networks of interconnected cortical and subcortical regions; the study investigated location of function within vmPFC but did not examine how these regions interact during prosocial learning; lesion mapping analyses could reveal additional areas of specialisation with a larger sample; considerable variability in the structure of vmPFC between individuals means sharp anatomical boundaries cannot be confirmed; reliance on natural lesions caused by vascular or haemorrhagic pathology leads to correlations among voxels that can bias estimated locations; no predefined hypothesis about lateralisation so lesions were mirrored; future studies with larger samples needed to investigate functional lateralisation; more complex learning tasks with forgetting rates could assess whether prosocial learning impairments become more pronounced.
- **limitations_categorized:** Limited network-level analysis; sample size (for VLSM subregion detection); individual anatomical variability; lesion correlation structure; lateralization not assessed; task simplicity; limited ecological validity.
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 8.5
- **wc_total:** 8.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params mean fitted values: LOW — not reported in main text or supplement; only group-level statistical comparisons available - model recovery (WC rule 6): HIGH confidence it was NOT done — no mention of model confusion matrix - preregistered: MEDIUM — not mentioned; likely not preregistered - coordinates: HIGH — extracted from Supplementary Table 9; note these are VLSM peaks (lesion-symptom mapping), not fMRI activation peaks
- **cannot_find:** - Mean fitted parameter values for the winning model (per group, per condition) - Model recovery analysis - Explicit preregistration statement
- **other_notes:** - This is a lesion study, not fMRI — the "implementation level" reflects VLSM (voxel-based lesion-symptom mapping) rather than task-based fMRI contrasts - The sgACC region identified converges with the region previously found to code prosocial PEs in fMRI by Lockwood et al. (2016) — the overlap is noted explicitly in the paper (Fig. 6J) - Patricia Lockwood is senior author on this paper - The winning model was the same across all three participant groups (HC, vmPFC, LC) with exceedance probabilities of 100%, 96.59%, and 98.09% respectively - The "other participant" was actually a confederate; no participant reported disbelieving - Modeling was run separately for each group due to large differences in group sizes
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = target
- spec_neural = dedicated
- spec_target = partly
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_valence_asymmetry
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_topic_prosocial_altruism
- tax_topic_prosocial_altruism
