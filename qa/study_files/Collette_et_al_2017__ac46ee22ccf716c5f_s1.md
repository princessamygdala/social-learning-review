# Collette et al. (2017)

- **study_id:** `ac46ee22ccf716c5f_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Collette, S., Pauli, W. M., Bossaerts, P., & O'Doherty, J. (2017). Neural computations underlying inverse reinforcement learning in the human brain. *eLife*, 6, e29718. https://doi.org/10.7554/eLife.29718
- **citation_short:** Collette et al. (2017)
- **doi:** 10.7554/eLife.29718
- **publication_type:** peer-reviewed journal
- **year:** 2017.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Institute of Technology, Pasadena, United States; 3Florey Institute of Neuroscience; ethatknowledgetocomputehis/herownsubjectiveexpectedvaluefortakingdistinctactions; Division of Humanities and Social Sciences , California Institute of Technology,; ethe agent’s actions to infer the hidden or unobservable properties ofthe envi-; etherthiscomputationalprocessisimplementedinthehumanbrain,participants; mitationlearning,theobserverlearnsnothingaboutthestructure; University of Melbourne, Melbourne, Australia; 4California; mpiricalevidencethatsubjectivepreferencesemergein; emails: sven.collette@gmail
- **code_url:** 

## Computational level
- **study_focus:** Observational learning via inverse reinforcement learning — inferring hidden reward distributions from observed actions of agents with similar and dissimilar preferences
- **study_focus_short:** Observational learning via inverse reinforcement learning
- **learning_mode_description:** - Learning mode: Learning the hidden distribution of food outcomes over slot machines by observing another agent's choices, then using that knowledge to guide own choices   - Learning from:     - Source type (social): other (observed agent — similar or dissimilar preference agent)     - Source content (social): action/policy (repeated binary slot machine choices)   - Learning about:     - Target type (non-social): world (reward/outcome distribution over slot machines)     - Target content (non-social): outcome (probability distribution of food items across slot machines)
- **task_description:** Participants observed two agents (one with similar, one with dissimilar food preferences) repeatedly choose between pairs of three slot machines with hidden food outcomes, then chose between the same slot machines themselves to maximize preferred food delivery.
- **task_paradigm:** Observational learning task
- **players:** Single agent (participant/observer), multi-target (2 agents: 1 similar-preference, 1 dissimilar-preference)
- **n_players:** dyadic (2)
- **partner_type:** unclear
- **stimuli:** Fractals (slot machine labels), food items (hidden outcomes ranked by preference), pseudo video-feed of agents
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Inverse RL outperformed imitation RL in BMS for both similar and dissimilar conditions (exceedance probability ~1.0 for inverse RL) - Participants performed significantly worse in dissimilar vs. similar condition (one-tailed p = 0.04 after Fisher transform) - dmPFC encoded expected value in agent-referential (not self-referential) preference space for both similar and dissimilar agents (no significant difference between conditions, t-test p > 0.5) - TPJ/pSTS, pre-SMA, and dorsal striatum encoded inverse RL entropy reduction (belief update) signals (whole-brain FWE cluster-corrected p < 0.05) - dmPFC value signal predicted behavioral performance on the slot machine task (r = 0.39, p < 0.01) - TPJ/pSTS entropy signal did not predict behavioral performance (r = 0.17, p > 0.25) - Confusion matrices confirmed inverse RL and imitation RL are distinguishable models
- **effect_size:** - Spearman rank correlation between participant and agent choices: rs_sim = 0.7 (similar), rs_dis = 0.6 (dissimilar) - dmPFC value-performance correlation: R = 0.39, p < 0.01 - TPJ/pSTS entropy-performance correlation: R = 0.17, p > 0.25
- **learning_from:** Other (observed agent's slot machine choices); social agents with known similar/dissimilar food preferences
- **learning_about:** World; hidden probability distribution of food outcomes over slot machines  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Approximate inverse RL (Bayesian-inspired belief updating over outcome distribution matrix D; parameters: ε_c(i) and ε_u(i) updating constants for chosen/unchosen arms, softmax β)
- **model_family:** Bayesian
- **model_class:** Inverse RL
- **all_models_tested:** [   {"name": "Inverse RL (approximate)", "family": "Bayesian/inverse RL", "n_params": "not explicitly stated (ε_c, ε_u updating vectors + β)", "metric": "BIC/BMS"},   {"name": "Imitation RL", "family": "Rescorla-Wagner", "n_params": 3, "metric": "BIC/BMS"},   {"name": "Counterfactual Imitation RL (cf-Imitation RL)", "family": "Rescorla-Wagner", "n_params": 4, "metric": "BIC/BMS"},   {"name": "Preference learning", "family": "Bayesian belief updating", "n_params": "not specified", "metric": "BIC/BMS"} ]
- **model_mb_mf:** MB (model-based — inverse RL infers internal model of outcome distributions)
- **model_params:** - ε_c(i): updating constants for chosen arm outcome probabilities (3 values for 3 outcomes) [S] — agent's choice updates beliefs about reward distribution - ε_u(i): updating constants for unchosen arm outcome probabilities (3 values for 3 outcomes) [S] — agent's non-choice updates beliefs - β (b): softmax exploitation intensity / choice temperature - θ (imitation RL only): inversion parameter reflecting perceived similarity [S] - η (imitation RL only): learning rate - Mean fitted values: not reported
- **social_param:** ε_c(i) and ε_u(i) — updating constants that capture how the observer updates beliefs about slot machine outcome distributions based on the observed agent's choices; these implicitly encode the observer's model of the agent's preference-driven behavior
- **social_param_name:** ε_c
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC, Bayesian Model Selection (BMS) with exceedance probabilities (random effects)
- **how_model_fit:** individual-level-fit (MLE via fmincon with 3 random starting points, iterated for decay factor)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors from inverse RL model: outcome prediction in agent-referential space, entropy/KL divergence update signal)
- **contrast:** - Inverse RL outcome prediction (agent-referential expected value) at slot machine onset → dmPFC (x=0, y=40, z=40; whole-brain FWE cluster-corrected p < 0.05) - Inverse RL entropy reduction (KL divergence between posterior and prior) at agent choice revelation → TPJ/pSTS, pre-SMA, dorsal striatum (whole-brain FWE cluster-corrected p < 0.05) - BMS: inverse RL vs. imitation RL in anatomical dmPFC ROI → anterior dmPFC exceedance probability > 0.95 for inverse RL - dmPFC value signal correlated with social information integration (SI) index (R = 0.39, p < 0.01)
- **key_regions:** Agent-referential expected value in anterior dmPFC; inverse RL belief updating (entropy reduction) in TPJ/pSTS, pre-SMA, and dorsal striatum; chosen value at participant choice in rostromedial PFC (dissimilar condition) and ventral striatum (similar condition, liberal threshold).
- **key_regions_abbrev:** VS, dStr, striatum, mPFC, dmPFC, TPJ, STS
- **coordinates_peak:** - dmPFC (outcome prediction, agent-referential EV): 0, 40, 40 - TPJ/pSTS (entropy/belief update signal): 59, y~from figure (exact y not stated in text) - pre-SMA (entropy/belief update signal): -5, 12, z~from figure - Dorsal striatum (entropy/belief update signal): coordinates shown in figure but exact values not provided in text  Note: The paper reports peak coordinates for dmPFC explicitly (x=0, y=40, z=40). For other regions, coordinates appear in figures (Figure 4 shows approximate slice locations: pre-SMA x=-5, y=12; striatum; TPJ/pSTS x=59) but exact peak MNI coordinates are not provided in the main text. The paper references source data files (DOI: 10.7554/eLife.29718.007, .009) that contain coordinate tables, but these are external supplementary data files not embedded in the paper text.
- **analysis_type:** both (whole-brain analysis with FWE cluster correction + ROI analysis using anatomical dmPFC from Harvard-Oxford atlas for BMS)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 43 (50 recruited, 7 excluded for head motion/technical issues; 23 male, 20 female; ages 18-40, mean 27.1 ± 4.9 years)
- **population_category:** healthy adults
- **population_age_range:** 18–40
- **ecological_validity:** Moderate constraints: participants believed they observed real agents (confirmed in debrief), but agents were artificial; food outcomes provided real incentive (consumed at end); slot machine task is abstract and lab-based; social interaction is unidirectional (observation only, no reciprocal exchange).
- **eligibility_flag:** 
- **concerns:** - Exact number of free parameters for inverse RL model not explicitly stated; updating constants ε_c and ε_u are vectors (3 values each) but constraints on fitting these are unclear - Peak MNI coordinates for TPJ/pSTS, pre-SMA, and dorsal striatum not provided in main text (only dmPFC peak is explicitly stated); coordinate tables referenced as external source data files - No parameter recovery or model recovery confusion matrix for the full model set (confusion matrix shown only for inverse RL vs. imitation RL in dissimilar condition) - Mean fitted parameter values not reported - Preference learning phase fMRI results deferred to future manuscript
- **limitations_reported:** Not explicitly stated in a dedicated limitations section. The authors note: the approximate inverse RL is a reduced-form model because the complete Bayesian inverse RL is computationally intractable; the paradigm involves artificial agents rather than real social partners; the paper focuses narrowly on inverse RL and defers preference learning results to a subsequent manuscript; only two social agents tested (one similar, one dissimilar).
- **limitations_categorized:** model simplification/approximation; limited ecological validity (artificial agents); limited generalizability (only two agent types); incomplete reporting (preference learning deferred)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** Partial
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - coordinates_peak: MEDIUM — only dmPFC peak (0, 40, 40) explicitly stated; other region coordinates approximated from figure slice labels; source data files referenced but not embedded - model_params (n_params for inverse RL): LOW — exact count of free parameters not clearly stated; unclear how ε vectors were constrained - model_params (mean fitted values): MEDIUM — not reported for any model - wc_guidelines rule 3 (simulate): MEDIUM — confusion matrices generated but unclear if full parameter space simulation conducted before fitting - wc_guidelines rule 6 (model recovery): MEDIUM — confusion matrix only for 2 main models in dissimilar condition
- **cannot_find:** - Exact peak MNI coordinates for TPJ/pSTS, pre-SMA, and dorsal striatum (referenced in source data DOIs but not in main text) - Exact number of free parameters for inverse RL model - Mean fitted parameter values for all models - Supplement not available (no separate supplement file; paper references figure supplements and source data as part of eLife's supplementary system)
- **other_notes:** This is an eLife paper where figure supplements and source data are hosted online rather than as a traditional PDF supplement. The source data files (DOIs .007 and .009) likely contain the full coordinate tables but were not accessible as separate files in the papers folder. The paper elegantly dissociates inverse RL from imitation by using agents with similar vs. dissimilar preferences, enabling identification of agent-referential vs. self-referential value representations. The finding that dmPFC encodes values in agent-referential space is a key contribution to understanding mentalizing during observational learning.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_mentalizing_inference
- spec_depth = parametric
- spec_locus = source
- spec_neural = dedicated
- spec_source = partly
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_mod_mentalizing_inference
- tax_model_MB
- tax_model_bayesian
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_social_weight
- tax_rr_primary_topic = mentalizing
- tax_rr_secondary_topic = imitation_emulation
- tax_rr_topic_imitation_emulation
- tax_rr_topic_mentalizing
- tax_topic_imitation_emulation
- tax_topic_mentalizing
