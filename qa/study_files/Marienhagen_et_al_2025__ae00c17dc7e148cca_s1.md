# Marienhagen et al. (2025)

- **study_id:** `ae00c17dc7e148cca_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Marienhagen, J., Blum Moyse, L., Schakowski, A., Kahl, B., Davidson, J., El Hady, A., Kurvers, R. H. J. M., & Deffner, D. (2025). Bridging reinforcement-learning and drift-diffusion modeling to uncover the cognitive processes underlying collective foraging. [Preprint/Manuscript].
- **citation_short:** Marienhagen et al. (2025)
- **doi:** Not reported in manuscript text. No DOI found.
- **publication_type:** preprint (no journal name, no doi; references cite 2024/2025 works; appears to be an unpublished manuscript/preprint)
- **year:** 2025.0
- **field_of_study:** Psychology
- **affiliations_raw:** 
- **code_url:** 

## Computational level
- **study_focus:** Collective foraging; social information integration; value shaping vs. decision biasing
- **study_focus_short:** Collective foraging
- **learning_mode_description:** Learning from group members' foraging locations and fish catches about patch quality in a two-patch foraging environment. - Learning from:   - Source type (social): group (4 other co-foragers)   - Source content (social): actions (observed foraging locations) and outcomes (observed fish catches) - Learning about:   - Target type (non-social): world (patch quality / resource distribution)   - Target content (non-social): state (which patch has higher catch probability)
- **task_description:** Participants controlled avatars in an immersive virtual fishing environment, freely switching between two lakes with different fish-catch probabilities over 36 trials (75-105 seconds each). They foraged either alone, in groups of 5 observing only others' locations, or in groups of 5 observing both locations and catches.
- **task_paradigm:** Social network learning
- **players:** Multi-agent (groups of 5), symmetric; also single agent (alone condition)
- **n_players:** 
- **partner_type:** human (live)
- **stimuli:** Virtual lake environment with avatar characters; fish catch symbols (fish appearing above avatars); binary catch/no-catch feedback
- **method:** behavioural
- **method_full:** behavioural (immersive-reality lab experiment)
- **main_result:** - Groups outperformed solitary foragers in environments with sparse rewards and large patch differences, sometimes exceeding optimal Bayesian agents (posterior contrast catches vs. alone at Catch Ratio=0.5: .04 [.01, .08]) - RL framework: Value-shaping model (environment-specific) won for No Catches condition (elpd_diff = -263.82 for asocial vs. flexible VS); VS_l VS_r won for Catches condition (elpd_diff = 0) - DDM framework: Value-shaping model won for No Catches condition; DB_l DB_r won for Catches condition (F = 0.032) - Both frameworks accurately reproduced empirical learning trajectories across conditions - Frameworks diverged on cognitive mechanism for catch integration: RL supported value shaping, DDM supported decision biasing
- **effect_size:** - Bayesian logistic regression posterior contrasts (90% HPDI): Catch Ratio 0.5 vs. 0.95: .32 [.23, .40]; Max Catch 0.9 vs. 0.5: .08 [.04, .17] - No Catches vs. Alone (Catch Ratio=0.5): .04 [.01, .07]; Catches vs. Alone: .04 [.01, .08] - RL model comparison (elpd_diff): Flexible VS_l vs. Asocial (NC): -263.82 (SE=25.99); VS_l VS_r vs. DB_l DB_r (C): -196.21 (SE=24.88) - DDM fitness values: Asocial F=0.037; VS (NC) F=0.028; DB_l DB_r (C) F=0.032
- **learning_from:** Group (other co-foragers); observed foraging locations and fish catches
- **learning_about:** World; patch quality (which lake has higher catch probability)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** RL: Alone = Asocial RW (α_P,-, α_P,+, β_Q, β_H); NC = Flexible VS_l RW (environment-specific α_VS,l); C = VS_l VS_r RW (α_VS,l via σ, α_VS,l,r). DDM: Alone = Asocial DDM (µ, B, y_b, τ_y); NC = VS DDM (α_VS,l, η); C = DB_l DB_r DDM (α_DB,l, η, α_DB,r)
- **model_family:** Drift-diffusion
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Asocial RL (ARL_H,±)", "family": "RW", "n_params": 4, "metric": "PSIS-LOO (elpd)"}, {"name": "ARL_H,±[m]", "family": "RW", "n_params": "4+env", "metric": "PSIS-LOO"}, {"name": "ARL_H,±[m,r]", "family": "RW", "n_params": "4+env", "metric": "PSIS-LOO"}, {"name": "DB_l (NC)", "family": "social RW", "n_params": 5, "metric": "PSIS-LOO"}, {"name": "VS_l (NC)", "family": "social RW", "n_params": 5, "metric": "PSIS-LOO"}, {"name": "Flexible VS_l[m,r] (NC)", "family": "social RW", "n_params": "5+env", "metric": "PSIS-LOO"}, {"name": "Flexible DB_l[m,r] (NC)", "family": "social RW", "n_params": "5+env", "metric": "PSIS-LOO"}, {"name": "VS_l VS_r (C)", "family": "social RW", "n_params": 6, "metric": "PSIS-LOO"}, {"name": "DB_l DB_r (C)", "family": "social RW", "n_params": 6, "metric": "PSIS-LOO"}, {"name": "VS_r (C)", "family": "social RW", "n_params": 5, "metric": "PSIS-LOO"}, {"name": "DB_l (C)", "family": "social RW", "n_params": 5, "metric": "PSIS-LOO"}, {"name": "DB_l VS_r (C)", "family": "social RW", "n_params": 6, "metric": "PSIS-LOO"}, {"name": "DB_r (C)", "family": "social RW", "n_params": 5, "metric": "PSIS-LOO"}, {"name": "VS_l (C)", "family": "social RW", "n_params": 5, "metric": "PSIS-LOO"}, {"name": "VS_l DB_r (C)", "family": "social RW", "n_params": 6, "metric": "PSIS-LOO"}, {"name": "Asocial DDM", "family": "DDM", "n_params": 4, "metric": "loss function F"}, {"name": "VS DDM (NC)", "family": "social DDM", "n_params": 6, "metric": "loss F"}, {"name": "DB DDM (NC)", "family": "social DDM", "n_params": 6, "metric": "loss F"}, {"name": "DB_l DB_r DDM (C)", "family": "social DDM", "n_params": 7, "metric": "loss F"}, {"name": "VS_l DB_r DDM (C)", "family": "social DDM", "n_params": 7, "metric": "loss F"}, {"name": "DB_l VS_r DDM (C)", "family": "social DDM", "n_params": 7, "metric": "loss F"}, {"name": "VS_l VS_r DDM (C)", "family": "social DDM", "n_params": 7, "metric": "loss F"}, {"name": "Bayesian optimal forager", "family": "Bayesian", "n_params": 0, "
- **model_mb_mf:** MF (RL models); N/A (DDM models are evidence accumulation, not RL)  ---  ### IMPLEMENTATION LEVEL
- **model_params:** RL winning models: - α_P,- : personal learning rate for negative RPE (Alone: 0.16 [0.13, 0.19]; C VS_l VS_r: 0.15 [0.12, 0.17]) - α_P,+ : personal learning rate for positive RPE (Alone: 0.07 [0.06, 0.08]; C: 0.04 [0.03, 0.05]) - β_Q : inverse temperature (Alone: 8.50 [7.63, 9.29]; C: 9.01 [8.06, 9.92]) - β_H : persistence (Alone: 3.52 [3.37, 3.65]; C: 3.61 [3.48, 3.73]) - σ_VS,l,r [S]: relative weight of catches vs. locations in VS (C: 0.37 [0.22, 0.50]) - α_VS,l,r [S]: social learning weight for combined VS (C: 0.04 [0.03, 0.04]) DDM winning models: - µ : foraging cost (Alone: 1.4 s^-1; NC VS: 1.2 s^-1; C DB_l DB_r: 2.2 s^-1) - B : noise amplitude (Alone: 0.15 s^-1; NC VS: 0.47 s^-1; C: 1.8 s^-1) - y_b : initial patch inference (Alone: 0.42; NC: 0.38; C: 0) - τ_y : timescale of patch inference (Alone: 5.6 s; NC: 5.1 s; C: 11 s) - α_VS,l [S] (NC): 0.5 s^-1; η (NC): 0.61 - α_DB,l [S] (C): 0.13 s^-1; η_l (C): 0.13; α_DB,r [S] (C): 17 s^-1 - θ: decision threshold (fixed at -5)
- **social_param:** - α_VS,l [S]: social learning weight for integrating others' locations via value shaping (RL) - α_VS,r [S]: social learning weight for integrating others' catches via value shaping (RL) - σ_VS,l,r [S]: relative weight of catches vs. locations in combined social coupling (RL) - α_VS,l [S] (DDM NC): strength of social evidence accumulation from locations - α_DB,l, α_DB,r [S] (DDM C): social decision-biasing weights for locations and catches
- **social_param_name:** σ_VS,l,r
- **social_param_value:** 0.37
- **social_param_sd:** 
- **social_param_range:** 0.22–0.50
- **model_comparison_metric:** PSIS-LOO (elpd; for RL models); simulation-based curve-fitting loss function F (for DDM models)
- **how_model_fit:** RL: individual-level-fit (hierarchical Bayesian via Stan/HMC); DDM: simulate-and-compare (CMA-ES optimization of loss function between simulated and observed accuracy trajectories)
- **data_type_fit_to:** choice behavior (RL: second-by-second location choices; DDM: accuracy trajectories over time)

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N=90 (58 female, 31 male, 1 non-binary; M_age=27.01, SD_age=6.84; organized in 18 groups of 5); 294,840 unique data points
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** High for a lab study; immersive-reality fishing task with real-time group interaction, continuous free movement between patches, and ecologically motivated foraging context. However, limited to 2-patch binary choice with stationary reward probabilities.
- **eligibility_flag:** 
- **concerns:** DDM fitting procedure used simulation-based curve fitting rather than likelihood-based inference, which aggregated over trials and individuals, potentially obscuring individual-level processes. The two frameworks used fundamentally different fitting approaches (hierarchical Bayesian for RL vs. CMA-ES optimization for DDM), making direct model comparison across frameworks difficult. No formal cross-framework model comparison metric. Environment-specific social learning parameters in the flexible RL model increase parameter count substantially.
- **limitations_reported:** Inferences drawn from computational models about the broader underlying theory thereby necessarily depend on the explicit or implicit assumptions encoded in their structure"; "the timescale and granularity of the model necessarily does not match the timescale and granularity of the data used to evaluate it" (for DDMs); equifinality as constraint on inference from aggregated summary statistics; "several competing processes can be compatible with the same empirical pattern"; DDMs could not be fitted using likelihood-based inference; "Future research could use larger behavioral datasets and simulation-based inference with neural networks that can be more sensitive to subtle differences between alternative generative processes
- **limitations_categorized:** model comparison limitations; equifinality; fitting procedure differences across frameworks; limited generalizability of DDM inference; no neural data
- **preregistered:** No
- **wc_rule1:** Yes (task designed to engage social information integration in foraging)
- **wc_rule2:** Yes (extensive model space: multiple RL and DDM variants with value shaping and decision biasing)
- **wc_rule3:** Yes (numerical simulations conducted before fitting; simulated predictions for different social learning weights)
- **wc_rule4:** Yes (RL: hierarchical Bayesian via Stan/HMC; DDM: CMA-ES optimization)
- **wc_rule5:** No (no parameter recovery reported)
- **wc_rule6:** No (no model recovery / confusion matrix reported)
- **wc_rule7:** Yes (systematic model comparison: PSIS-LOO for RL; loss function for DDM)
- **wc_rule8:** Yes (posterior simulations from winning models compared to empirical trajectories)
- **wc_rule9:** Yes (inferred parameters analyzed and compared to optimal values from simulations)
- **wc_rule10:** Partial (no mention of data/code sharing; acknowledged DFG funding)
- **wc_score:** 0
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - doi (LOW: no DOI found in manuscript text; likely preprint without assigned DOI) - publication_type (MEDIUM: inferred as preprint from absence of journal name and DOI) - wc_rule10 (MEDIUM: no explicit data/code availability statement found) - model_params for flexible VS RL in NC condition (MEDIUM: environment-specific parameters not individually reported; only noted that α_VS,l[m,r] < 0.02)
- **cannot_find:** DOI; data/code availability statement; preregistration statement; exact number of parameters for environment-specific flexible RL models; individual-level parameter distributions
- **other_notes:** This paper is primarily a methods-comparison paper, directly contrasting RL and DDM frameworks within the same paradigm. Both frameworks reproduce behavior well but diverge on the cognitive mechanism (value shaping vs. decision biasing) for integrating observed catches. The authors favor the RL interpretation due to stronger fitting procedure. The paper is closely related to Wu et al. (2025) "Adaptive mechanisms of social and asocial learning in immersive collective foraging" (also in the papers folder) -- potential overlap in paradigm/sample should be checked for duplicate flagging. Supplementary materials are embedded in the same text file.
- **re_extract_flag:** FALSE (full text including supplement was accessible)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_multiplayer_live
- rr_tax_mod_social_info_search
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = parametric
- spec_locus = source+context
- spec_source = social
- tax_domain_A_influence_transmission
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_multiplayer_live
- tax_mod_social_info_search
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_drift_diffusion
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_drift_diffusion
- tax_rr_model_family = drift_diffusion
- tax_rr_param_social_weight
- tax_rr_primary_topic = cooperation
- tax_rr_secondary_topic = social_info_use
- tax_rr_topic_cooperation
- tax_rr_topic_social_info_use
- tax_social_nonsocial_comparison
- tax_topic_cooperation
- tax_topic_social_info_use
