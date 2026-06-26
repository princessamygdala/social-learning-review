# Seid-Fatemi & Tobler (2015)

- **study_id:** `af2ad2f27c098206e_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Seid-Fatemi, A., & Tobler, P. N. (2015). Efficient learning mechanisms hold in the social domain and are implemented in the medial prefrontal cortex. *Social Cognitive and Affective Neuroscience*, *10*(5), 735–743. https://doi.org/10.1093/scan/nsu130
- **citation_short:** Seid-Fatemi & Tobler (2015)
- **doi:** 10.1093/scan/nsu130
- **publication_type:** peer-reviewed journal
- **year:** 2015.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** mited cognitive resources that would be conserved if we value to us as they may provide us with relevant information that is; Laboratory for Socialand Neural SystemsResearch, Department ofEconomics, University ofZurich, Zurich, Switzerland; ethatblockingdoesindeedoccurinthesocialdomainanditdoessotoa; DepartmentofEconomics,UniversityofZurich,andBertramGerber; lable to us inthe environment (not resulting in block-; etheritalsodoeswhentheylearnaboutothers(cid:2)rewards; mittedfoodpreferences,thereappearstobelittleblocking; ethodstoaddressthisquestion
- **code_url:** 

## Computational level
- **study_focus:** Observational reward learning; blocking effect in social vs. individual reward learning domains
- **study_focus_short:** Observational reward learning
- **learning_mode_description:** - Learning mode: Learning to associate novel cues with monetary reward outcomes for self (individual condition) and for others (social condition), with efficiency tested via the blocking paradigm   - Learning from:     - Source type (non-social): world       - Source content (non-social): outcome (monetary reward presence/absence paired with visual cues)   - Learning about:     - Target type (social): other (two anonymous female volunteers)       - Target content (social): outcome (whether other person receives monetary reward)     - Target type (non-social): self       - Target content (non-social): outcome (whether self receives monetary reward)
- **task_description:** Participants learned to associate abstract visual stimuli with monetary rewards for themselves (individual condition) or for two anonymous others (social condition) across three phases: pretraining (stimulus-outcome associations), compound conditioning (blocked vs. control compounds), and test (blocked vs. non-blocked stimuli presented alone without reward). On each trial, participants indicated via keypress whether they expected reward or no reward for self or other.
- **task_paradigm:** Social conditioning
- **players:** Single agent (participant), multi-target (2 anonymous female volunteers as reward recipients in social condition)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Abstract colored shapes on white background, monetary outcomes (CHF), text descriptions of other persons
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Blocking occurred in both social and individual domains: Y (control) stimuli elicited more reward key presses than X (blocked) stimuli in social (t(37) = 3.07, p < 0.005) and individual (t(37) = 2.48, p < 0.05) conditions - Degree of social blocking correlated with individual blocking across participants (R² = 0.45) - mPFC (2, 60, 16) showed stronger activation for reward-predicting A vs neutral B stimuli in social condition (t(37) = 5.41, whole-brain FWE corrected) - mPFC blocking effect (Y vs X) correlated with behavioral blocking in social condition (6, 60, 12; t(36) = 3.63, FWE small-volume corrected) - mPFC showed preferential social vs individual activation for A vs B (8, 56, 12; t(37) = 4.52, whole-brain FWE cluster corrected) and Y vs X (12, 56, 10; t(37) = 3.57, FWE small-volume corrected) - dmPFC (10, 30, 38) tracked decreasing prediction errors in BY vs AX trials during social condition (t(37) = 4.65, FWE cluster corrected)
- **effect_size:** - R² = 0.45 (correlation between social and individual blocking degree across participants) - t(37) = 5.41 (mPFC: A > B social, whole-brain FWE) - t(36) = 3.63 (mPFC: Y vs X correlation with behavioral blocking, social) - t(37) = 4.52 (mPFC: A vs B social > individual, whole-brain FWE cluster) - t(37) = 3.57 (mPFC: Y vs X social > individual, FWE SVC) - t(37) = 4.65 (dmPFC: BY vs AX parametric modulator, social, FWE cluster)
- **learning_from:** World; reward outcome (monetary reward presence/absence) paired with visual cues
- **learning_about:** Other (two anonymous others); whether other receives monetary reward. Also self; whether self receives monetary reward (individual condition).  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Rescorla-Wagner (1 free parameter: α learning rate; δ_t = α_t(λ_t − V_t))
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Rescorla-Wagner", "family": "Rescorla-Wagner", "n_params": 1, "metric": "fitted to behavioral keypresses"}]
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): estimated at 0.10 for social condition, 0.15 for individual condition (no significant difference between conditions). Free parameter fitted to trial-by-trial percentage of reward keypress responses in BY trials averaged across participants. - δ (prediction error): δ_t = α_t(λ_t − V_t), where V_t is associative strength of all stimuli present in trial t, λ_t is reward in trial t. Derived, not fitted.
- **social_param:** No explicit social parameter. The same RW model was fitted separately for social and individual conditions, yielding separate learning rates (α_social = 0.10, α_individual = 0.15), but no dedicated social modulation parameter was included in the model.
- **social_param_name:** 
- **social_param_value:** 0.10
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** N/A — only one model tested; prediction errors from RW model used as parametric modulators in fMRI GLM
- **how_model_fit:** Group-level fit (model fitted to trial-by-trial average keypress responses across participants in BY trials)
- **data_type_fit_to:** Choice behavior (trial-by-trial reward keypress responses)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors) — prediction errors derived from RW model used as parametric modulators of compound conditioning regressors in univariate GLM
- **contrast:** - A > B (social): reward expectation in social domain; mPFC (2, 60, 16; t(37) = 5.41, whole-brain FWE cluster corrected) - Y vs X correlated with behavioral blocking (social): mPFC (6, 60, 12; t(36) = 3.63, FWE SVC) - A vs B social > A vs B individual: mPFC (8, 56, 12; t(37) = 4.52, whole-brain FWE cluster corrected) - Y vs X social > Y vs X individual: mPFC (12, 56, 10; t(37) = 3.57, FWE SVC); lateral PFC (26, 60, 6; FWE cluster corrected) - BY parametric modulator > AX parametric modulator (social): dmPFC (10, 30, 38; t(37) = 4.65, FWE cluster corrected) - A > B (individual): vmPFC (−4, 40, −6; t(37) = 3.81, FWE SVC) - Y vs X correlated with behavioral blocking (individual): vmPFC (−6, 42, −4; t(36) = 3.84, FWE SVC)
- **key_regions:** Social reward expectation and blocking in dorsal mPFC; prediction error decrease during social compound conditioning in dmPFC; individual reward expectation and blocking in vmPFC; preferential social (vs. individual) blocking in mPFC extending to lateral PFC.
- **key_regions_abbrev:** vmPFC, mPFC, dmPFC, lPFC
- **coordinates_peak:** - mPFC (A > B social): 2, 60, 16 - Posterior cingulate cortex (A > B social): −6, −52, 16 - Rolandic operculum (A > B social > individual): −60, −6, 10 - Precuneus (A > B social > individual): 8, −54, 58 - mPFC (A > B social > individual): 8, 56, 12 - Middle occipital gyrus (A > B social > individual): 48, −78, 20 - Lateral PFC (Y > X social > individual): 26, 60, 6 - Parietal cortex (BY_PM > AX_PM social): 34, −62, 38 - dmPFC (BY_PM > AX_PM social): 10, 30, 38 - mPFC blocking correlation social (Y vs X ~ behavioral blocking): 6, 60, 12 - vmPFC (A > B individual): −4, 40, −6 - vmPFC blocking correlation individual (Y vs X ~ behavioral blocking): −6, 42, −4 - mPFC (Y > X social > individual): 12, 56, 10
- **analysis_type:** Both (whole-brain FWE cluster-level correction and ROI/small-volume correction using 10–15 mm spheres around a priori coordinates)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 38 (17 female; aged 21.0 ± 0.4 years; range: 18–28)
- **population_category:** healthy adults
- **population_age_range:** M=21.0 (SD=0.4)
- **ecological_validity:** Low ecological validity. Participants never met the reward recipients face-to-face; social condition involved reading brief descriptions of anonymous others. Abstract cue-reward associations do not closely approximate naturalistic social learning contexts. However, the use of real monetary payouts to actual other persons provides some ecological grounding.
- **eligibility_flag:** 
- **concerns:** Only one computational model tested (RW), so no formal model comparison was performed. Model was fitted to group-averaged behavioral data rather than individual-level fitting, limiting insight into individual differences in model parameters. The social condition involves learning about rewards for anonymous strangers with minimal social information, which is a relatively impoverished social context. Prediction errors used as parametric modulators were derived from group-averaged fits, not individual-level fits.
- **limitations_reported:** Authors note they cannot rule out that neural results might generalize to blocking effects in causal learning and may be partly driven by explicit verbal reasoning; they acknowledge they did not find significantly stronger vmPFC activation for individual vs. social condition, so cannot conclude ventral mPFC is specific for self-relevant rewards; they note that contextual factors determining vmPFC contribution to social learning remain to be determined; they acknowledge that the relatively dorsal mPFC finding for social blocking warrants further investigation of mechanisms underlying the development of blocking in the social domain.
- **limitations_categorized:** Limited ecological validity; task simplicity; no formal model comparison; group-level fitting only; limited social context (anonymous strangers); potential confound with explicit reasoning
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 4.0
- **wc_total:** 4.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - social_param: MEDIUM — no explicit social parameter in the model; social vs. individual learning rates were estimated separately but not as a formal model parameter - model_params (fitted values): MEDIUM — learning rates (0.10 social, 0.15 individual) reported but fitted to group-averaged data, not individual-level - how_model_fit: HIGH — explicitly described as fitted to "trial-by-trial percentage of reward keypress responses in BY trials, averaged across participants" - wc_guidelines rule 8: MEDIUM — coded as Partial because neural PE modulator provides indirect validation but no formal posterior predictive check was reported
- **cannot_find:** Supplement not accessible (referenced as "Supplementary data are available at SCAN online" but no supplement file available in the papers folder). Supplementary Table S1 (trial numbers per phase/condition) and Supplementary Figures S1–S2 (prediction error time courses, individual vmPFC results) could not be verified. No additional model details, parameter recovery, or coordinate tables could be checked.
- **other_notes:** This paper uses a within-subject design comparing social and individual blocking. The RW model is used primarily as a tool to generate prediction error time courses for fMRI parametric modulation rather than as a competitive model comparison exercise. The paper references Supplementary Table S1 and Supplementary Figures S1–S2, but these were not accessible. The supplement may contain additional coordinate tables or modeling details. Supplement not accessible.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = dedicated
- spec_target = social
- tax_domain_A_influence_transmission
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = social_info_use
- tax_rr_topic_social_info_use
- tax_topic_social_info_use
