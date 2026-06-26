# Babur et al. (2024)

- **study_id:** `a2cdcaf4b59eacb91_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Babur, B. G., Leong, Y. C., Pan, C. X., & Hackel, L. M. (2024). Neural responses to social rejection reflect dissociable learning about relational value and reward. *Proceedings of the National Academy of Sciences*, *121*(49), e2400022121. https://doi.org/10.1073/pnas.2400022121
- **citation_short:** Babur et al. (2024)
- **doi:** 10.1073/pnas.2400022121
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** miting step on social connection: two ways to build positive; ether they successfully matched (a rewarding; emails: lhackel@usc.edu
- **code_url:** https://osf.io/zc8er/

## Computational level
- **study_focus:** Learning about relational value and reward from social acceptance/rejection; social affiliation learning
- **study_focus_short:** Learning about relational value and reward from social acceptance/rejection · social affiliation learning
- **learning_mode_description:** - Learning mode: Learning from acceptance/rejection feedback about others' relational value and reward outcomes to guide social partner choice   - Learning from:     - Source type (social): other (Decider partners)       - Source content (social): outcome (rank feedback revealing relational value; match/no-match acceptance outcome)   - Learning about:     - Target type (social): other (Decider partners)       - Target content (social): state (mental state; how much others value the participant — relational value) **and** outcome (probability of rewarding acceptance)
- **task_description:** Participants repeatedly chose between two Decider avatars to try to match with for an economic trust game. Feedback revealed how highly the chosen Decider ranked the participant relative to other players (relational value) and whether they successfully matched (rewarding outcome), with rank and match probability orthogonally manipulated across Decider types.
- **task_paradigm:** Trust game
- **players:** Single agent (participant), multi-target (8 Deciders; 4 with explicit rank feedback, 4 with hidden rank feedback)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Avatars (gender-matched), rank feedback (numerical rank 1st-8th), match/no-match outcome, trust game point allocation
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - Participants chose partners based on both relational value and rewarding outcomes; hybrid model best fit (protected exceedance probability = 1; median w = 0.52)   - Rank feedback predicted stay/switch choices (b = 0.21, SE = 0.06, z = 3.56, OR = 1.23)   - Outcome feedback predicted stay/switch choices (b = 0.22, SE = 0.05, z = 4.23, OR = 1.24)   - Unsigned rank model updating correlated with BOLD in social rejection network (dACC, vACC, AI, vlPFC) at pFWE < 0.05   - Signed outcome updating correlated with bilateral VS BOLD at pFWE < 0.05   - RSA: neural similarity in rejection network predicted subjective perceptions of being liked (M = 0.11, SD = 0.20, t(39) = 3.59)   - RSA: trial-by-trial rank belief similarity predicted neural pattern similarity (M = 0.01, SD = 0.02, t(39) = 3.08)   - RSA: trial-by-trial outcome belief similarity predicted neural pattern similarity (M = 0.03, SD = 0.03, t(39) = 5.17)   - Ratings of being liked influenced by rank (F(1,41) = 20.39, $\eta^2_p$ = 0.33) and outcome (F(1,41) = 13.76, $\eta^2_p$ = 0.25)   - Voxel importance overlap (Decider-Rank vs Decider-Outcome) predicted individual differences in subjective rating bias (r = 0.57)
- **effect_size:** - Main Results:   - Participants chose partners based on both relational value and rewarding outcomes; hybrid model best fit (protected exceedance probability = 1; median w = 0.52)   - Rank feedback predicted stay/switch choices (b = 0.21, SE = 0.06, z = 3.56, OR = 1.23)   - Outcome feedback predicted stay/switch choices (b = 0.22, SE = 0.05, z = 4.23, OR = 1.24)   - Unsigned rank model updating correlated with BOLD in social rejection network (dACC, vACC, AI, vlPFC) at pFWE < 0.05   - Signed outcome updating correlated with bilateral VS BOLD at pFWE < 0.05   - RSA: neural similarity in rejection network predicted subjective perceptions of being liked (M = 0.11, SD = 0.20, t(39) = 3.59)   - RSA: trial-by-trial rank belief similarity predicted neural pattern similarity (M = 0.01, SD = 0.02, t(39) = 3.08)   - RSA: trial-by-trial outcome belief similarity predicted neural pattern similarity (M = 0.03, SD = 0.03, t(39) = 5.17)   - Ratings of being liked influenced by rank (F(1,41) = 20.39, $\eta^2_p$ = 0.33) and outcome (F(1,41) = 13.76, $\eta^2_p$ = 0.25)   - Voxel importance overlap (Decider-Rank vs Decider-Outcome) predicted individual differences in subjective rating bias (r = 0.57)
- **learning_from:** Other (Decider partners); rank feedback (relational value cue) and match/no-match acceptance outcomes (reward cue)
- **learning_about:** Other (Decider partners); how much others value the participant (relational value as internal model) and probability of rewarding interaction outcomes  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** Bayesian belief updating (2 belief distributions: rank ~ Normal, outcome ~ Beta; weighted average choice rule with w and $\beta$)
- **model_family:** Bayesian
- **model_class:** PE learning / Belief updating
- **all_models_tested:** - {"name": "Hybrid (w free)", "family": "Bayesian belief updating", "n_params": 2, "metric": "BMS (protected exceedance probability)"} - {"name": "Outcome only (w = 0)", "family": "Bayesian belief updating", "n_params": 1, "metric": "BMS (protected exceedance probability)"} - {"name": "Rank only (w = 1)", "family": "Bayesian belief updating", "n_params": 1, "metric": "BMS (protected exceedance probability)"}
- **model_mb_mf:** Bayesian
- **model_params:** - w: weighting parameter for combining rank-based value and outcome-based value (0 = outcomes only, 1 = ranks only) [S]; median = 0.52, mean = 0.48 - $\beta$: inverse temperature (softmax); median = 1.51, mean = 2.46
- **social_param:** w — weighting parameter determining relative reliance on relational value (rank-based beliefs about how much others value the participant) vs. rewarding outcomes (match probability) when choosing social partners
- **social_param_name:** w
- **social_param_value:** 0.48
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Bayesian Model Selection (BMS) with protected exceedance probability; log model evidence via Laplace approximation
- **how_model_fit:** individual-level-fit (maximum a posteriori estimation per participant)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) + RSA
- **contrast:** - Unsigned rank model updating > baseline (dACC, vACC, AI, vlPFC, caudate, STS) — pFWE < 0.05 - Signed outcome updating (positive) > baseline (bilateral VS, mOFC) — pFWE < 0.05 - Negative signed outcome updating > baseline (bilateral TPJ/supramarginal gyrus) — pFWE < 0.05 - RSA: Decider identity encoding in social rejection network ROI - RSA: trial-by-trial rank belief similarity and outcome belief similarity with neural pattern similarity - ROI analyses in dACC [8, 24, 24] and vACC [4, 36, -4] from meta-analysis
- **key_regions:** Unsigned relational value updating in dACC, vACC, AI, vlPFC (social rejection network); reward outcome learning in bilateral VS and mOFC; negative outcome responses in bilateral TPJ/supramarginal gyrus. RSA showed relational value representations in rejection network regions predicted subjective perceptions.
- **key_regions_abbrev:** OFC, dACC, ACC, TPJ, AI
- **coordinates_peak:** - ROI from meta-analysis — dACC: 8, 24, 24 - ROI from meta-analysis — vACC: 4, 36, -4 - Note: The paper reports whole-brain cluster-level results corrected at pFWE < 0.05, but exact peak MNI coordinates for the whole-brain activations (AI, vlPFC, VS, caudate, STS, mOFC, TPJ) are not provided as numerical tables in the main text or supplement. Figures show statistical maps but do not list coordinate tables.
- **analysis_type:** both (whole-brain parametric modulator analyses + ROI analyses using 10mm spheres from meta-analysis coordinates)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 42 (40 planned for fMRI; 2 replaced due to scanner issues but included in behavioral analyses; 22 females; age 22.36 +/- 4.60 years); all right-handed, English fluent, no psychiatric/neurological history
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Moderate. Task dissociates relational value from rewarding outcomes, which mirrors some real-world scenarios (e.g., job rankings vs. getting hired, team selection). However, interactions are with computer-generated Deciders, not real people, limiting ecological validity. Trust game component adds some realism.
- **eligibility_flag:** 
- **concerns:** (1) All "other players" were computer-generated, not real social agents — participants were deceived into believing they were interacting with real people. (2) Peak MNI coordinates for whole-brain activations are not reported as numerical tables — only as figures. (3) The Bayesian model has no individual difference parameters for belief updating (only for choice weighting), which the authors acknowledge as a limitation. (4) Relatively small sample (N = 40 for fMRI).
- **limitations_reported:** The present model did not incorporate any parameters that would allow individual differences in updating beliefs; the only individual differences modeled concerned how participants combined rank and outcome information in choice. The present model thus reflects an ideal observer model regarding updating. Future work can extend the model by incorporating systematic deviations from an ideal observer, which might further explain individual differences in idiosyncratic perceptions as reported at the end of the task."; Authors advise caution interpreting null results for social pain hypothesis; TPJ activation for negative outcomes could reflect social pain or mentalizing computations — ambiguity acknowledged.
- **limitations_categorized:** limited model complexity (no individual differences in updating); small sample size; null result interpretation; ambiguity in functional interpretation of brain regions
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
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - coordinates_peak: MEDIUM confidence — ROI coordinates are from a prior meta-analysis and clearly reported; whole-brain peak coordinates are NOT reported as numerical values in main text or supplement (only shown in figures) - preregistered: LOW confidence — no mention of preregistration found in paper or supplement
- **cannot_find:** - Exact peak MNI coordinates for whole-brain activations (AI, vlPFC, VS, caudate, STS, mOFC, TPJ) — not reported as numerical tables in main text or supplement; only displayed in figure maps - Preregistration status
- **other_notes:** This paper cleanly dissociates two types of social learning (relational value updating vs. reward outcome learning) with distinct neural substrates. The Bayesian model is relatively simple (2 free parameters) but well-validated through simulation, parameter recovery, and model recovery. The RSA analyses provide convergent evidence linking model-derived beliefs to neural representations. Data are publicly available on OSF. The paper appeared in PNAS in 2024. The supplement confirms all Wilson & Collins criteria are met — an unusually thorough modeling validation for this literature.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_bayesian
- tax_param_PE_signal
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_PE_signal
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_approval_reward
- tax_rr_secondary_topic = reputation_learning
- tax_rr_topic_reputation_learning
- tax_rr_topic_social_approval_reward
- tax_topic_reputation_learning
- tax_topic_social_approval_reward
