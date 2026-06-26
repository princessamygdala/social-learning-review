# Xu et al. (2023)

- **study_id:** `a8209482cdec5baea_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Xu, Y., Guo, W., Huang, G., & Qu, C. (2023). Adaptive learning strategies in purely observational learning. *Current Psychology, 42*, 27593–27605. https://doi.org/10.1007/s12144-022-03904-3
- **citation_short:** Xu et al. (2023)
- **doi:** 10.1007/s12144-022-03904-3
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Psychology
- **affiliations_raw:** Center for Studies of Psychological Application, South; ether the outcome information is available to the; College of Xinghai Conservatory of Music,; University, Guangzhou, China; emails: guowei_judy@hotmail.com, m13121209038@163.com, cherish1119@163.com
- **code_url:** 

## Computational level
- **study_focus:** Observational learning — comparing individual learning (IL), action-only observational learning (AL), and action-outcome observational learning (AOL), with a focus on how demonstrator skill modulates computational strategies in AL.
- **study_focus_short:** Observational learning
- **learning_mode_description:** - Learning mode: Learning from observing a demonstrator's choices (with or without outcome feedback) about stimulus-reward contingencies   - Learning from:     - Source type (social): other (demonstrator)       - Source content (social): action/policy (demonstrator's choices); outcome (feedback, in AOL condition)   - Learning about:     - Target type (non-social): world (stimulus-reward contingencies)       - Target content (non-social): outcome (which option yields reward)
- **task_description:** Participants completed an adapted two-arm bandit task with three conditions (IL, AL, AOL). In each trial, a learning stage (observing a demonstrator's choices with/without feedback, or making own choices with feedback) was followed by a no-feedback testing stage where participants made their own choices.
- **task_paradigm:** Two-armed bandit
- **players:** Single agent (participant), single demonstrator (artificial, sex-matched); between-subjects: skilled demonstrator (SD) group vs. unskilled demonstrator (UD) group.
- **n_players:** single agent (1)
- **partner_type:** human (recorded)
- **stimuli:** Abstract black-and-white images (pairs), binary feedback (+1/-1), face photos of demonstrators (from Chicago Face Database).
- **method:** behavioural
- **method_full:** Behavioural
- **main_result:** - IL and AOL led to better performance than AL (F(2,44) = 20.327, p < .001, η²p = 0.360) - Demonstrator skill × learning condition interaction on optimal choice (F(1,44) = 4.200, p = .046, η²p = 0.087) - Skill effect significant only in AL condition (F(1,44) = 8.217, p = .006, η²p = 0.157) - SD group: Action Preference (AP) model won for AL (XP = 0.9959, MF = 0.5820) - UD group: Decision Bias (DB) model won for AL (XP = 0.9963, MF = 0.6022) - Imitation × skill interaction (F(1,44) = 6.727, p = .013, η²p = 0.133) - Learning rates in AL smaller than IL and AOL across both groups (SD: F(2,22) = 20.652, p < .001, η²p = 0.652; UD: F(2,20) = 15.324, p < .001, η²p = 0.605)
- **effect_size:** η²p = 0.360 (condition effect on optimal choice); η²p = 0.087 (interaction); η²p = 0.157 (skill in AL); η²p = 0.133 (imitation interaction); Cohen's d = 0.587 (imitation above chance in UD-AL); XP = 0.9959 (AP model, SD); XP = 0.9963 (DB model, UD)
- **learning_from:** Other (demonstrator's choices and/or outcomes); social source.
- **learning_about:** World; stimulus-reward contingencies (which abstract image yields reward).  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Two winning models depending on group: - SD group: Action Preference (AP) model for AL + RW for IL/AOL (α_individual, α_obs.AL, α_obs.AOL, β) - UD group: Decision Bias (DB) model for AL + RW for IL/AOL (α_individual, α_DB.AL, α_obs.AOL, β)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - Model 1: AP for AL + RW for IL/AOL; family: Rescorla-Wagner; n_params: 4 (β, α_individual, α_obs.AL, α_obs.AOL); metric: LL/XP/MF - Model 2: NULL for AL + RW for IL/AOL; family: random choice + RW; n_params: 3 (β, α_individual, α_obs.AOL); metric: LL/XP/MF — eliminated by simulation failure - Model 3: DB for AL + RW for IL/AOL; family: Decision Bias + RW; n_params: 4 (β, α_individual, α_DB.AL, α_obs.AOL); metric: LL/XP/MF - Model 4: VS for AL + RW for IL/AOL; family: Value-Shaping + RW; n_params: 4 (β, α_individual, α_VS.AL, α_obs.AOL); metric: LL/XP/MF
- **model_mb_mf:** MF (all models are model-free reinforcement learning)
- **model_params:** - β: inverse temperature (softmax); limited 0.1–1.0 (step 0.1); varied across runs - α_individual: learning rate for IL condition - α_obs.AL [S]: learning rate for AL condition (AP model) / imitation rate (DB model) - α_obs.AOL [S]: learning rate for AOL condition - Demonstrator parameters (fixed, not fitted): α = 0.3, β = 0.4 for SD; random for UD - Mean fitted values: Not reported for individual parameters (only ANOVA on learning rates shown in Fig. 4g/h)
- **social_param:** α_obs.AL [S] — observational learning rate in AL condition (governs how strongly the learner integrates demonstrator action preference or imitates demonstrator choice); α_obs.AOL [S] — observational learning rate in AOL condition.
- **social_param_name:** α_obs.AL
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Log-likelihood (LL), Bayesian model selection: exceedance probability (XP) and model expected frequency (MF) via VBA toolbox. Note: AIC/BIC mentioned but LL used directly because surviving models had equal number of parameters.
- **how_model_fit:** Individual-level fit (fmincon in MATLAB, minimizing negative log-likelihood per participant per run)
- **data_type_fit_to:** Choice behavior (testing stage choices)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 46 (1 excluded from original 47); SD group n = 24 (14 women, mean age 19.7 ± 1.6), UD group n = 22 (13 women, mean age 19.2 ± 1.6). All ≥18 years, university students.
- **population_category:** undergraduates
- **population_age_range:** M=19.7
- **ecological_validity:** Low — abstract stimuli (random black-and-white images), artificial demonstrator (computer-generated choices presented as previous participant), binary outcomes. Limited social interaction (no real dyadic exchange). However, the manipulation of demonstrator skill adds some ecological nuance.
- **eligibility_flag:** 
- **concerns:** - Small sample size (n = 22–24 per group) - Demonstrator was artificial (not a real person), which may limit social ecological validity - No parameter recovery or model recovery reported - Mean fitted parameter values not reported (only ANOVAs on learning rates) - Model 2 (NULL) eliminated by simulation rather than formal model comparison, reducing comparison to 3 models - No code/data shared publicly (available on request only) - β parameter constrained to discrete steps (0.1 to 1.0, step 0.1) rather than continuous optimization — unusual and potentially limiting
- **limitations_reported:** The adapted two-armed bandit task had a limitation: in IL, omission, correct, and incorrect responses have the same informative value, but for AL and AOL, omission is negative feedback because of missing demonstrator's choice information; the study proposed a new learning strategy but did not determine how people identify their situations (whether they can distinguish demonstrator skill from AL alone or need AOL); learning strategies in some situations might be more complex than modeled; more detailed experiments and models are needed; cognitive neuroscience research is expected to reveal the nature of observational learning.
- **limitations_categorized:** Task design confound; limited understanding of strategy selection mechanism; model simplicity; sample size; no neuroimaging data.
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - Mean fitted parameter values: not reported individually, only learning rate ANOVAs (MEDIUM confidence that learning rates shown in Fig. 4g/h are the α parameters) - model_family for DB model: classified as "Decision Bias" but it is technically a simple imitation/decision-bias heuristic, not a standard RL family (MEDIUM) - Formula for DB model APE: paper states APE_t = 1 - 0.5 = 0.5 constant, meaning the DB model reduces to a fixed bias — this is unusual (HIGH, directly stated)
- **cannot_find:** - Exact mean fitted parameter values (β, individual α values per group) - Whether any parameter bounds were hit during optimization - Supplement: no supplement found for this paper
- **other_notes:** - This is a single study (1 row in CSV) - The paper finds different winning models for different subgroups (SD vs UD), which is an interesting design feature — the AP model wins only for skilled demonstrator group, DB model for unskilled - The AP model is novel to this paper: it uses action consistency (whether demonstrator repeated their last choice) as a pseudo-reward to drive value updating - The DB model's APE formula as written (APE_t = 1 - 0.5) yields a constant 0.5, meaning the "imitation rate" α_DB.AL effectively becomes a fixed additive bias to choice probability — this simplifies to a static imitation tendency rather than a learning process - No supplement exists for this paper
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- tax_domain_A_influence_transmission
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = imitation_emulation
- tax_rr_secondary_topic = social_info_use
- tax_rr_topic_imitation_emulation
- tax_rr_topic_social_info_use
- tax_topic_imitation_emulation
- tax_topic_social_info_use
