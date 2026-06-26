# Hackel et al. (2019)

- **study_id:** `a9b9f1c6d36ab97ce_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Hackel, L. M., Berg, J. J., Lindström, B. R., & Amodio, D. M. (2019). Model-based and model-free social cognition: Investigating the role of habit in social attitude formation and choice. *Frontiers in Psychology*, *10*, 2592. https://doi.org/10.3389/fpsyg.2019.02592
- **citation_short:** Hackel et al. (2019)
- **doi:** 10.3389/fpsyg.2019.02592
- **publication_type:** peer-reviewed journal
- **year:** 2019.0
- **field_of_study:** Psychology
- **affiliations_raw:** University,UnitedStates way in which learning related to self-reported attitudes: among participants who relied; University,UnitedStates participants preferred advisors who could provide large future rewards as well as; DepartmentofPsychology,UniversityofSouthernCalifornia,LosAngeles,CA,UnitedStates,2DepartmentofPsychology,; University,NewYork,NY,UnitedStates,3DepartmentofPsychology,UniversityofAmsterdam,Amsterdam,; ether habit-like processes may also; UniversityofMichigan,UnitedStates; ethecontributionofhabits; sectionofthejournal; emails: david.amodio@nyu.edu, lhackel@usc.edu
- **code_url:** 

## Computational level
- **study_focus:** Social attitude formation through instrumental reinforcement learning; role of model-based vs. model-free (habitual) learning in forming social impressions of interaction partners
- **study_focus_short:** Social attitude formation through instrumental reinforcement learning
- **learning_mode_description:** - Learning mode: Learning from financial reward outcomes provided by social partners (advisors) about the reward value and likeability of those partners   - Learning from:     - Source type (social): other (financial advisor)       - Source content (non-social): outcome (monetary reward from stock performance)   - Learning about:     - Target type (social): other (financial advisor)       - Target content (social): state (mental state; likeability/attitude toward advisor) and outcome (reward value of choosing that advisor)
- **task_description:** Participants played the role of "Client" and chose between pairs of financial advisors (represented by cartoon avatars) who each deterministically led to one of two stocks; participants then received a reward (0-9 points) based on the stock's fluctuating performance over 150 trials in a two-step sequential decision task.
- **task_paradigm:** Two-step task
- **players:** Single agent (participant), multi-target (4 advisors in 2 pairs)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Cartoon avatars (advisors), abstract stocks ("Axiom" and "Zephyr"), monetary point outcomes (0-9)
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - Model-based learning in social choice: main effect of reward on staying with same stock (b = 1.47, SE = 0.07, z = 19.80)   - Model-free learning in social choice: Reward x Start State interaction (b = 0.22, SE = 0.03, z = 6.45)   - Model-based values predicted post-task liking of advisors (b = 0.30, SE = 0.14, t(71.46) = 2.17)   - Model-free values marginally predicted post-task liking (b = 0.16, SE = 0.09, t(162.97) = 1.82)   - w parameter x model-free values interaction on liking (b = -0.24, SE = 0.08, t(148.01) = -2.97): participants with greater model-free learning showed stronger model-free influence on attitudes   - Simple effect for high model-free learners (w at 25th percentile = 0.70): model-free values predicted attitudes (b = 0.31, SE = 0.10, t(155.32) = 3.11)   - Simple effect for high model-based learners (w at 75th percentile = 1.0): model-free values did not predict attitudes (b = -0.03, SE = 0.11, t(162.01) = -0.31)
- **effect_size:** Standardized regression coefficients (b values from mixed-effects models) reported above; no Cohen's d, r-squared, or other traditional effect sizes reported. Mean w parameter = 0.83.
- **learning_from:** Other (financial advisors); reward outcomes from stock performance following advisor choice
- **learning_about:** Other (financial advisors); reward value and likeability/attitude toward advisors  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Hybrid MB/MF RL (w weighting parameter; model-free Q-values at stage 1 and stage 2; model-based forward planning; w = 0.83 mean)
- **model_family:** MB/MF hybrid
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Hybrid MB/MF RL", "family": "Hybrid MB/MF Q-learning", "n_params": "not specified in main text", "metric": "MAP estimation with empirical priors"}] - Note: Only one computational model is described as fitted. The paper also reports a lagged regression (model-agnostic) analysis but this is a statistical test, not a competing computational model.
- **model_mb_mf:** MB/MF hybrid
- **model_params:** - w: weighting parameter for relative influence of MB vs. MF learning (0 = purely MF, 1 = purely MB); mean = 0.83 [S — indexes balance of social learning strategies] - Additional parameters (learning rates, softmax temperature) referenced in Supplementary Table S1 but not reported in main text. Cannot verify exact parameter names/values without supplement.
- **social_param:** w (weighting parameter) — indicates the relative reliance on model-based (goal-directed, prospective) vs. model-free (habitual, retrospective) learning during social partner choice. Mean fitted value = 0.83.
- **social_param_name:** w
- **social_param_value:** 0.83
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** MAP estimation with empirical priors (Gershman, 2016; Kool et al., 2017). No formal model comparison across competing models reported (only one hybrid model fitted).
- **how_model_fit:** individual-level-fit (MAP estimation per participant)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 65 (69 recruited; 4 excluded for missed trials >20%); 42 male, 27 female; recruited via Amazon Mechanical Turk. Age not reported.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low ecological validity. Advisors represented by cartoon avatars in an abstract stock-investment framing. No real social interaction. Online task via AMT. Deterministic advisor-stock transitions are unrealistic. However, the financial advisor framing provides some intuitive social context.
- **eligibility_flag:** 
- **concerns:** - Only one computational model was fitted; no competing models tested against each other (e.g., pure MB, pure MF, alternative hybrid specifications). - Full model parameters and fitted values are in Supplementary Table S1, which was not accessible for extraction. Parameter details beyond w are unknown. - The model-free effect on liking was only marginally significant (p = 0.07) at mean w levels. - Social framing is minimal — advisors are cartoon avatars, and the "social" nature of the task is primarily a cover story for a standard two-step RL task. - No age data reported for participants. - Data available only "on request" (not openly shared).
- **limitations_reported:** Questions have been raised as to whether additional strategies may contribute to observed effects of model-free learning in sequential decision tasks"; "people may use learning and choice strategies not encapsulated by our task and analyses, moving beyond the two approaches studied here"; "there is some debate on whether — and to what extent — model-free learning maps on to traditional definitions of habitual control"; "participants might have generated unexpected task representations (e.g., grouping advisors under abstract action representations or representing four end states) that would yield different inferences about MB vs. MF learning
- **limitations_categorized:** Task validity (two-step task may not cleanly dissociate MB/MF); limited ecological validity; alternative computational strategies not modeled; construct validity (MF learning ≠ habit debate); possible alternative task representations
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 4.5
- **wc_total:** 4.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params: LOW confidence — only w parameter reported in main text; learning rate(s), inverse temperature, and other parameters referenced as being in Supplementary Table S1, which was not accessible - effect_size: MEDIUM confidence — regression coefficients (b) reported but no standardized effect sizes (d, r-squared, etc.) - wc_guidelines rule 3 (simulate): MEDIUM confidence — simulated predictions shown in figures but unclear if this constitutes pre-fitting simulation - wc_guidelines rule 5 (parameter recovery): LOW confidence — may be in supplement, but cannot verify
- **cannot_find:** - Full model parameter list (learning rates, temperature, etc.) — referenced in Supplementary Table S1 - Number of free parameters in the computational model - Participant age range - Full lagged regression coefficients — referenced in Supplementary Table S2 - Full liking regression coefficients — referenced in Supplementary Table S3 - Supplement not accessible (not in papers folder). Flagging: "Supplement not accessible.
- **other_notes:** - This is a single-study paper (1 study). - The paper adapts the Kool et al. (2016, 2017) two-step task to a social context with financial advisor avatars. - The hybrid MB/MF model follows Kool et al. (2017) exactly; no novel model development. - The w parameter (mean = 0.83) indicates participants were predominantly model-based, consistent with prior two-step task findings. - The paper's contribution is primarily in applying the MB/MF framework to social impression formation, not in computational model innovation. - Supplement not in papers folder; model details (parameter list, fitted values, model equations) could not be fully verified.
- **re_extract_flag:** false (full text was available; however, supplement was not accessible, so some algorithmic-level details are incomplete)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = partly
- tax_domain_B_inference_modelling_others
- tax_mod_experiential
- tax_model_MB
- tax_model_MB_MF_hybrid
- tax_model_rescorla_wagner
- tax_param_MB_MF_balance
- tax_param_social_bonus
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_MB_MF_hybrid
- tax_rr_model_family = MB_MF_hybrid
- tax_rr_param_MB_MF_balance
- tax_rr_primary_topic = trait_impression
- tax_rr_topic_trait_impression
- tax_topic_trait_impression
