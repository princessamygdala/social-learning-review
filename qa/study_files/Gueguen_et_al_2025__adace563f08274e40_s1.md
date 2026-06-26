# Gueguen et al. (2025)

- **study_id:** `adace563f08274e40_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Gueguen, M., Cutler, J., Drew, D., Apps, M. A. J., Jeyaretna, D. S., Husain, M., Manohar, S. G., & Lockwood, P. L. (2025). Ventromedial prefrontal cortex lesions disrupt learning to reward others. *Brain*. https://doi.org/10.1093/brain/awaf056
- **citation_short:** Gueguen et al. (2025)
- **doi:** 10.1093/brain/awaf056
- **publication_type:** peer-reviewed journal---
- **year:** 2025.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Department of Experimental Psychology, University of Oxford, Anna Watts Building, Radcliffe; Centre for Human Brain Health, School of Psychology, UnivSersity of Birmingham, Edgbaston,; Centre for Human Brain Health, School of Psychology, University of Birmingham, Edgbaston,; Institute for Mental Health, School of Psychology, University of Birmingham, Edgbaston,; Department of Clinical Neurosciences, University of Oxford, Level 6, West Wing, John; Centre for Integrative N euroimaging, University of Oxford, FMRIB Building, John; Department of Neurology, John Radcliffe Hospital, Oxford, OX3 9DU,
- **code_url:** 

## Computational level
- **study_focus:** Prosocial reinforcement learning — how vmPFC damage causally disrupts learning to obtain rewards for others versus self versus no one, and which vmPFC subregions (sgACC, ACCg) are specifically involved
- **study_focus_short:** Prosocial reinforcement learning
- **learning_mode_description:** - Learning mode: Learning from one's own reward/no-reward outcomes to select stimuli that maximize rewards for self, other, or no one   - Learning from:     - Source type (non-social): self       - The participant's own choices generate outcomes     - Source content (non-social): outcome       - Binary reward feedback (0 or 100 points)   - Learning about:     - Target type (social): other (anonymous participant) — in prosocial condition     - Target type (non-social): self — in self condition     - Target type (non-social): world — in no one (control) condition     - Target content (social/non-social): stimulus       - Which abstract symbol is associated with higher reward probability
- **task_description:** Participants chose between two abstract symbols on each trial, one associated with 75% reward probability and one with 25%, across three recipient conditions (self, other, no one) in separate blocks. Points were converted to monetary reward for the relevant recipient (self, anonymous other, or no one).
- **task_paradigm:** Prosocial choice task
- **players:** Single agent (participant), single target (anonymous other participant, actually confederate); three groups: vmPFC lesion patients (n=28), lesion controls (n=21), healthy controls (n=124)
- **n_players:** network (5+)
- **partner_type:** confederate
- **stimuli:** Abstract symbols (Agathodaimon font letters), binary feedback (0 or 100 points), recipient cues (name of self/confederate/no one)
- **method:** lesion / behavioural
- **method_full:** Behavioural (lesion study with VLSM)
- **main_result:** - vmPFC patients were less accurate when learning to reward others vs. no one compared to both control groups (vmPFC vs. HC: OR = 0.76 [0.63, 0.91], Z = -2.91; vmPFC vs. LC: OR = 0.67 [0.52, 0.86], Z = -3.13) - vmPFC patients showed no self-benefitting advantage (self vs. no one: OR = 0.96, BF01 = 3.61, substantial evidence for null), unlike both control groups - vmPFC patients had lower positive PE learning rates for other vs. no one compared to HC (OR = 0.84, Z = -4.36) and LC (OR = 0.87, Z = -2.58) - vmPFC patients had higher negative PE learning rates for other vs. self compared to HC (OR = 1.06, Z = 2.11) and LC (OR = 1.13, Z = 3.16) - VLSM: damage to sgACC (area s24) specifically disrupted prosocial learning from positive PEs (other-no one: peak MNI +/-4, 20, -4; other-self: peak 8, 32, -20) - VLSM: damage to ACCg (areas 24a'/b') and sgACC disrupted prosocial learning from negative PEs (other-self: peaks at 8, 6, -16; +/-4, 10, -10; +/-2, 34, 8) - Damage to lateral vmPFC (area 13, peak 8, 26, -12) was associated with the self-no one positive PE learning rate difference
- **effect_size:** - Accuracy other-no one: vmPFC vs. HC OR = 0.76 [0.63, 0.91]; vmPFC vs. LC OR = 0.67 [0.52, 0.86] - Accuracy self-no one: vmPFC vs. HC OR = 0.82; vmPFC vs. LC OR = 0.75 - Positive PE LR other-no one: vmPFC vs. HC OR = 0.84 [0.78, 0.91]; vmPFC vs. LC OR = 0.87 [0.78, 0.97] - Negative PE LR other-self: vmPFC vs. HC OR = 1.06 [1.00, 1.12]; vmPFC vs. LC OR = 1.13 [1.05, 1.22] - BF01 for vmPFC self vs. no one accuracy = 3.61 (substantial evidence for null)  [HIGH — all directly reported]
- **learning_from:** Self; own reward outcomes (0 or 100 points) from chosen abstract symbols
- **learning_about:** Other (anonymous participant) in prosocial condition; self in self condition; no one (control); which stimulus maximizes rewards for the relevant recipient---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** RW with 6 learning rates and 1 temperature (6α1β): α_self_positive_PE, α_self_negative_PE, α_other_positive_PE, α_other_negative_PE, α_no_one_positive_PE, α_no_one_negative_PE, β
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "1α1β", "family": "Rescorla-Wagner", "n_params": 2, "metric": "LME, exceedance probability, BICint"} - {"name": "3α1β", "family": "Rescorla-Wagner", "n_params": 4, "metric": "LME, exceedance probability, BICint"} - {"name": "2α(S/O+N)1β", "family": "Rescorla-Wagner", "n_params": 3, "metric": "LME, exceedance probability, BICint"} - {"name": "2α(O/S+N)1β", "family": "Rescorla-Wagner", "n_params": 3, "metric": "LME, exceedance probability, BICint"} - {"name": "2α(N/S+O)1β", "family": "Rescorla-Wagner", "n_params": 3, "metric": "LME, exceedance probability, BICint"} - {"name": "3α3β", "family": "Rescorla-Wagner", "n_params": 6, "metric": "LME, exceedance probability, BICint"} - {"name": "0α1β (win-stay/lose-shift)", "family": "Win-stay/lose-shift", "n_params": 1, "metric": "LME, exceedance probability, BICint"} - {"name": "0α3β (win-stay/lose-shift)", "family": "Win-stay/lose-shift", "n_params": 3, "metric": "LME, exceedance probability, BICint"} - {"name": "6α_PE 1β (WINNING)", "family": "Rescorla-Wagner", "n_params": 7, "metric": "LME, exceedance probability, BICint"} - {"name": "6α_PE 3β", "family": "Rescorla-Wagner", "n_params": 9, "metric": "LME, exceedance probability, BICint"} - {"name": "4α_chosen 1β", "family": "Rescorla-Wagner", "n_params": 5, "metric": "LME, exceedance probability, BICint"} - {"name": "5α_chosen 1β", "family": "Rescorla-Wagner", "n_params": 6, "metric": "LME, exceedance probability, BICint"} - {"name": "6α_chosen 3β", "family": "Rescorla-Wagner", "n_params": 9, "metric": "LME, exceedance probability, BICint"}
- **model_mb_mf:** MF
- **model_params:** - α_self_positive_PE: learning rate for positive PEs in self condition [no mean reported] - α_self_negative_PE: learning rate for negative PEs in self condition [no mean reported] - α_other_positive_PE [S]: learning rate for positive PEs in other (prosocial) condition [no mean reported] - α_other_negative_PE [S]: learning rate for negative PEs in other (prosocial) condition [no mean reported] - α_no_one_positive_PE: learning rate for positive PEs in no one condition [no mean reported] - α_no_one_negative_PE: learning rate for negative PEs in no one condition [no mean reported] - β: inverse temperature (decision noise), single parameter across conditions [no mean reported]  [HIGH for parameter names; MEDIUM for mean values — paper reports medians were used for simulation but exact values not provided in text]
- **social_param:** α_other_positive_PE [S] and α_other_negative_PE [S] — learning rates for positive and negative prediction errors when learning to reward another person. These were the key parameters showing vmPFC-specific disruption relative to controls.
- **social_param_name:** α_other_positive_PE
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Log Model Evidence (LME), exceedance probability, integrated BIC (BICint)
- **how_model_fit:** Individual-level fit via iterative maximum a posteriori (MAP) with expectation-maximisation; run separately for each group
- **data_type_fit_to:** Choice behavior---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (lesion study with VLSM)
- **contrast:** - VLSM: positive PE learning rate (other - no one) — sgACC (area s24) - VLSM: positive PE learning rate (other - self) — sgACC (areas s24, 32) and lateral vmPFC (area 13) - VLSM: positive PE learning rate (self - no one) — lateral vmPFC (area 13) - VLSM: negative PE learning rate (other - self) — ACCg (areas 24a'/b') and sgACC (areas s24, 25) - VLSM: negative PE learning rate (self - no one) — area 14c
- **key_regions:** Damage to sgACC (area s24) disrupted prosocial learning from both positive and negative PEs; ACCg (areas 24a'/b') specifically disrupted prosocial negative PE learning rates relative to self; lateral vmPFC (area 13) associated with self-benefitting advantage in positive PE learning rates.
- **key_regions_abbrev:** vmPFC, mPFC, ACC, sgACC
- **coordinates_peak:** - Positive PE, other - no one: sgACC: +/-4, 20, -4 - Positive PE, other - self: sgACC/vmPFC: 8, 32, -20 - Positive PE, self - no one: lateral vmPFC (area 13): 8, 26, -12 - Negative PE, other - self: sgACC: 8, 6, -16 - Negative PE, other - self: sgACC: +/-4, 10, -10 - Negative PE, other - self: ACCg: +/-2, 34, 8 - Negative PE, self - no one: area 14c: +/-8, 14, -22  [HIGH — directly from Supplementary Table 9]
- **analysis_type:** whole-brain (VLSM with permutation-based TFCE, voxels included where at least 5 patients had damage)---  ### QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 173 (28 vmPFC lesion patients, age range 37-76, mean = 57, 15 females; 21 lesion controls, age range 28-74, mean = 56, 13 females; 124 healthy controls, age range 20-80, mean = 53, 71 females)
- **population_category:** mixed
- **population_age_range:** 37–76
- **ecological_validity:** Lab-based task with abstract symbols and binary outcomes. Prosocial element relies on belief manipulation (confederate as "other participant") with role-assignment procedure. Single anonymous interaction, no reciprocity possible. Real monetary incentives for self and other conditions. Limited ecological validity relative to real-world prosocial behaviour, though the monetary incentive structure is a strength.
- **eligibility_flag:** 
- **concerns:** (1) Lesion groups much smaller than HC group (28 and 21 vs. 124), which could affect power for between-group comparisons. (2) Mean fitted parameter values for the winning model are not reported (only medians used for simulation). (3) Natural lesions create correlated voxel damage patterns that can bias location estimates in VLSM. (4) Lesion maps were mirrored, precluding laterality analysis. (5) The "other" participant was a confederate — mild deception, though no participant reported disbelief. [MEDIUM]
- **limitations_reported:** Social behaviours and reinforcement learning rely on large networks of interconnected cortical and subcortical regions, and only within-vmPFC localisation was examined; future research should examine how these regions interact during prosocial learning; lesion mapping could reveal additional areas with a larger sample; variability in vmPFC structure means sharp anatomical boundaries cannot be confirmed; natural lesions lead to correlated voxel patterns that may bias estimated locations; no predefined hypothesis about lateralisation so lesions were mirrored; social influence on behaviour may also depend on medial prefrontal cortex and focal lesion effects on social influence should be examined
- **limitations_categorized:** Limited network-level analysis; sample size for lesion mapping; individual anatomical variability; lesion correlation bias (VLSM assumption); no laterality analysis; task simplicity (limited social complexity)
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
- **flagged_fields:** - model_params: MEDIUM — exact mean/median fitted parameter values for each group not reported in text or supplement (medians mentioned for simulation but values not listed) - wc_guidelines rule 10: MEDIUM — data/code availability stated as future ("upon publication") - wc_guidelines rule 6: No model recovery reported
- **cannot_find:** - Mean fitted parameter values for the winning model (medians used for simulation but not tabulated) - Model recovery analysis (confusion matrix across models)
- **other_notes:** This is a lesion study, not fMRI — the VLSM approach uses lesion overlap maps rather than BOLD signal. The winning model (6α1β with valence-split learning rates) was novel relative to previous work using the same task, which used 3α models. The paper provides strong converging evidence across accuracy, computational parameters, and lesion mapping. Patricia Lockwood is a senior author on this paper. Exceedance probability for winning model: HC 100%, vmPFC 96.59%, LC 98.09%.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = target
- spec_neural = dedicated
- spec_target = social
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
