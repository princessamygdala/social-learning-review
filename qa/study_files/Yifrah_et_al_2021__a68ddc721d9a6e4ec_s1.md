# Yifrah et al. (2021)

- **study_id:** `a68ddc721d9a6e4ec_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Yifrah, B., Ramaty, A., Morris, G., & Mendelsohn, A. (2021). Individual differences in experienced and observational decision-making illuminate interactions between reinforcement learning and declarative memory. *Scientific Reports*, *11*, 5899. https://doi.org/10.1038/s41598-021-85322-2
- **citation_short:** Yifrah et al. (2021)
- **doi:** 10.1038/s41598-021-85322-2
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Institute, Technion - Israel Institute of Technology, 31096 Haifa, Israel; Department of Neurobiology, University of Haifa, 3498838 Haifa, Israel; University of Haifa, Haifa, Israel; Institute of Information; Faculty of Medicine and; lable options; emails: amendels1@univ.haifa.ac.il
- **code_url:** 

## Computational level
- **study_focus:** Observational learning; individual differences in experiential vs. observational reinforcement learning and their interaction with declarative memory formation.
- **study_focus_short:** Observational learning
- **learning_mode_description:** - Learning mode: Learning from one's own and an observed other's choice outcomes about cue-reward contingencies, and examining how learning strategy affects incidental declarative memory.   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (reward/no reward feedback on experienced trials)     - Source type (social): other (second player / computerized simulation)       - Source content (social): outcome (observed choice-outcome contingencies)   - Learning about:     - Target type (non-social): world       - Target content (non-social): stimulus (cue-reward probability associations)
- **task_description:** Participants performed a probabilistic decision-making task choosing between two fractal cues with predetermined reward probabilities across 100 trials (50 experienced, 50 observed). In experienced trials they chose themselves; in observed trials they watched a simulated "second player" choose. Two cue pairs were used: a congruent pair (same 80:20 contingencies for both players) and an incongruent pair (reversed 70:30 vs. 30:70 contingencies). A surprise recognition memory test for trial-unique pictures followed.
- **task_paradigm:** Observational learning task
- **players:** Single agent (participant), dyadic (simulated second player acting as observation source)
- **n_players:** dyadic (2)
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract fractal images (cues), neutral IAPS pictures (trial-unique), binary feedback (smiley/sad emoji for reward/no reward)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Divided strategy group outperformed single strategy group across conditions (F(1,58) = 67.11, p < 0.0001)   - Learning was superior for congruent vs. incongruent pair (F(1,58) = 62.33, p < 0.0001)   - Strategy x pair type interaction (F(1,58) = 16.68, p < 0.0001)   - In divided strategy group, maximum cue value predicted memory for pictures in experienced trials (r = 0.85)   - In divided strategy group, maximum cue value did not predict memory in observed trials (r = 0.43, NS after correction)   - In single strategy group, no relationship between cue value and memory (experienced r = -0.03; observed r = -0.07)   - Fisher Z confirmed significant difference in value-memory correlations between groups   - Relative learning-rate difference correlated with high-reward choice on incongruent trials (r = 0.78)   - Estimated cue values predicted choice RT (single group r = -0.91; divided group r = -0.98)   - Divided strategy group showed trend for negative correlation between RL model fit and declarative memory (r = -0.33, p = 0.071)
- **effect_size:** - r = 0.85 (cue value vs. memory, divided group, experienced trials) - r = 0.78 (relative learning rate difference vs. incongruent trial performance) - r = -0.91, r = -0.98 (cue value vs. choice RT, single and divided groups) - r = -0.33 (model fit vs. d', divided strategy group, trend) - r = 0.816 (model fit vs. choice score, single group, congruent) - r = 0.619 (model fit vs. choice score, divided group, congruent) - r = 0.419 (model fit vs. choice score, divided group, incongruent)
- **learning_from:** Self (own experienced choice outcomes) and other (observed second player's choice outcomes); reward/no-reward feedback
- **learning_about:** World; cue-reward probability associations (stimulus values)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** RW with 2 learning rates: α_exp (experienced trials), α_obs (observed trials); 1 β (inverse temperature). "Divided" model. Update rule: Q(t+1) = Q(t) + α * δ, where δ = R - Q(t). Both chosen and unchosen values updated. Softmax choice function with β.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Single (1 learning rate)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BIC (cumulative: 4690.7)"},   {"name": "Divided (2 LRs: experienced/observed)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "BIC (cumulative: 4542.7)"},   {"name": "Pairwise (2 LRs: congruent/incongruent)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "BIC (cumulative: 4784.7)"},   {"name": "Four learning rates (exp/obs x con/incon)", "family": "Rescorla-Wagner", "n_params": 5, "metric": "BIC (cumulative: 4946.5)"} ]
- **model_mb_mf:** MF
- **model_params:** - α_exp [S]: learning rate for experienced trials. Individual fitted values in Table S1 (vary widely; e.g., divided group α_exp range ~0.001-1.0). - α_obs [S]: learning rate for observed trials. Individual fitted values in Table S1 (divided group α_obs typically near 0). - β: inverse temperature (Softmax). Individual fitted values in Table S1 (range ~0.49-100).  Note: For the "single" model, only one α is estimated. The key social parameter is the separation of α into α_exp and α_obs, which captures differential weighting of self vs. other information.
- **social_param:** α_obs — learning rate applied to observed (social) trials; captures how much weight the learner assigns to observed others' choice-outcome information relative to their own experienced outcomes.
- **social_param_name:** α_exp
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (cumulative across participants; also individual BIC for subject assignment)
- **how_model_fit:** individual-level-fit (MLE using Matlab fminsearch)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study)
- **key_regions:** N/A (behavioural study)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 75 (after exclusion of 4 from original 79; 47 females; ages 19-47, mean 24.9 +/- 4.8). Model assignment: 31 single strategy, 29 divided strategy, 15 unassigned.
- **population_category:** healthy adults
- **population_age_range:** 19–47
- **ecological_validity:** Low-moderate. Lab-based probabilistic gambling task with abstract fractal stimuli and simulated (not real) second player. Participants were told another person was playing but it was computerized. Limited ecological validity for real-world social observation.
- **eligibility_flag:** 
- **concerns:** The "second player" was actually a computerized simulation, not a real social agent — participants were deceived about the social nature of the task. The four-learning-rate model could not be recovered in the confusion matrix, limiting conclusions about more complex strategy differentiation. The incongruent pair was also inherently more difficult (70:30 vs 80:20), confounding congruence with difficulty. Correlation analyses between cue values and memory used binned data rather than trial-level modeling.
- **limitations_reported:** our design did not have sufficient power to accurately capture the four-rate model"; "This approach nicely accounted for a large fraction of the participants we dubbed 'unassigned'... however, this modeling approach yielded overall inferior model-fit scores"; the design "could not differentiate between these two forms of observational learning" (imitation vs emulation); "an alternative explanation for the reported findings is that rather than basing performance on reinforcement learning strategies, the presented cues could have been evaluated directly by a goal-directed valuation search process
- **limitations_categorized:** limited statistical power; model identifiability; task simplicity; alternative explanations not ruled out
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 8.0
- **wc_total:** 8.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM — individual fitted values reported in Table S1 but no group-level mean/SD summary statistics for parameters reported in main text - social_param: HIGH - wc_guidelines rule 3: MEDIUM — confusion matrix simulations described but unclear if task was simulated prior to data collection - wc_guidelines rule 5: HIGH (no parameter recovery reported) - ecological_validity: HIGH
- **cannot_find:** Group-level mean fitted parameter values (only individual values in Table S1, no summary statistics); no code or data sharing statement found.
- **other_notes:** This study is primarily about the interaction between RL and declarative memory, with the social/observational component serving as the manipulation that creates individual differences in learning strategy. The key social insight is that some individuals differentially weight self vs. other information sources (divided strategy) while others treat them equivalently (single strategy). The "second player" was simulated — this should be flagged as an automated social agent. The study nicely demonstrates how individual differences in social information weighting relate to memory formation.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- tax_domain_A_influence_transmission
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_primary_topic = social_info_use
- tax_rr_topic_social_info_use
- tax_topic_social_info_use
