# Schmid & Braun (2025)

- **study_id:** `a161e0ddcef2f9a88_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Schmid, G., & Braun, D. A. (2025). Human intergroup coordination in a hierarchical multi-agent sensorimotor task arises from concurrent co-optimization. *Scientific Reports*, *15*, 14849. https://doi.org/10.1038/s41598-025-97574-3
- **citation_short:** Schmid & Braun (2025)
- **doi:** 10.1038/s41598-025-97574-3
- **publication_type:** peer-reviewed journal
- **year:** 2025.0
- **field_of_study:** Psychology
- **affiliations_raw:** Faculty of Engineering, Computer Science and Psychology, Institute of Neural Information Processing, Ulm; Division of labor and specialization are common principles observed across all levels of biological; mited information processing capabilities,12,13 restricted access to sensory input,14,15 a; division of labour and specialization in sensorimotor tasks; laborative tasks by providing clear structure and reducing; laborate to accomplish a shared sensorimotor; laboration and mutual understanding; ether to process information and; emails: gerrit.schmid@uni-ulm.de
- **code_url:** 

## Computational level
- **study_focus:** Joint action learning / intergroup sensorimotor coordination / division of labor and specialization in multi-agent coordination
- **study_focus_short:** Joint action learning / intergroup sensorimotor coordination / division of
- **learning_mode_description:** - Learning mode: Learning from one's own and group members' sensorimotor actions about one's own contribution to a shared hierarchical sensorimotor task   - Learning from:     - Source type (social): group (own subgroup — sensor or actor group of 4 players)       - **joint** (actions are jointly produced by all group members; individual contributions are entangled)     - Source content (non-social): outcome (cursor/target displacement resulting from combined button presses)   - Learning about:     - Target type (non-social): world (one's own assigned movement direction / displacement contribution)     - Target content (non-social): action/policy (mapping from target difference vector angle to optimal button-press policy)
- **task_description:** Groups of 8 participants are split into a sensor group (4 players who observe cursor and target but cannot act) and an actor group (4 players who control the cursor but cannot see it). Each player has an unknown movement direction activated by a push-button; the ensemble must learn to coordinate so that the sensor group communicates target information to the actor group, which steers a cursor to the target.
- **task_paradigm:** Joint action / coordination
- **players:** Multi-agent (8 participants in 2 groups of 4), hierarchical (sensor group leads, actor group follows); 4 independent groups of 8 tested.
- **n_players:** 
- **partner_type:** human (live)
- **stimuli:** Computer screen displaying cursor sprite and target sprite; push-buttons (binary action); no verbal communication allowed.
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Group improvement rate increased significantly over time for both actor and sensor groups (Mann-Kendall: Z = 33.88, p < 10^-50 for actors; Z = 40.71, p < 10^-50 for sensors; Kendall's tau: τ = 0.827 and τ = 0.993 respectively) - Individual correct response rate showed significant monotonic increase (actors: τ = 0.192; sensors: τ = 0.943) - Mutual information between target angle and actor decisions increased significantly over time (Z = 39.38, τ = 0.961) - Action time correlations showed neighborhood relationships: players with similar displacement directions acted more in unison (actors: p = 2.488 × 10^-4; sensors: p = 1.067 × 10^-6) - Thompson sampling (Bayesian) model and bounded rationality model successfully replicated human behavior; model-free hierarchical RL failed - Cross-correlation lag between sensor-to-actor responses: 4–5 time steps (500–625 ms) for humans
- **effect_size:** Kendall's τ = 0.827 (actor improvement), τ = 0.993 (sensor improvement), τ = 0.192 (actor individual correct response), τ = 0.943 (sensor individual correct response), τ = 0.961 (mutual information increase). No Cohen's d, r², or β values reported.
- **learning_from:** Group (own subgroup); joint sensorimotor outcomes (cursor/target displacement from combined actions of all group members)
- **learning_about:** World; own assigned movement direction and optimal policy for button-press responses  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Thompson sampling (Bayesian); von Mises belief over displacement direction, time-dependent learning rate α(t) = 0.51A_t + 1.03A_{t-1} + 0.89A_{t-2}; sigmoid activation ρ = 2.73; ε-greedy ε = 0.23
- **model_family:** Bayesian
- **model_class:** PE learning
- **all_models_tested:** - {"name": "Thompson sampling (Bayesian)", "family": "Bayesian belief updating", "n_params": 3, "metric": "grid search matching human performance metrics (trajectory length, improvement rate, mutual information)"} - {"name": "Bounded rational decision network", "family": "Information-theoretic bounded rationality", "n_params": 2, "metric": "grid search matching human performance metrics"} - {"name": "Reinforcement learning (model-free)", "family": "Reinforcement learning", "n_params": "not specified", "metric": "task completion (failed)"} - {"name": "Perceptron learning (ANN)", "family": "Artificial neural network", "n_params": "not specified", "metric": "task completion (failed)"} - {"name": "Feudal RL (hierarchical)", "family": "Hierarchical reinforcement learning", "n_params": "not specified", "metric": "task completion (failed without pretraining)"}
- **model_mb_mf:** MB (Thompson sampling maintains internal model / belief about displacement direction)
- **model_params:** - ρ = 2.73 (sigmoid activation function parameter, controls action stochasticity) - ε = 0.23 (ε-greedy exploration parameter) - α(t) = time-dependent learning rate: 0.51A_t + 1.03A_{t-1} + 0.89A_{t-2} (weights observations after button press) - θ_i^g = (μ̂, κ̂) — von Mises mean direction and concentration for each player (updated online) - R, Θ — resultant vector parameters of Bayesian posterior (updated each trial) - For bounded rational model: β = 2.3 (inverse temperature / rationality parameter); decision network depth = 4
- **social_param:** No explicitly designated "social" parameter. The learning rate function α(t) implicitly handles the social credit assignment problem (disentangling own contribution from others' actions), but is not labeled as social by the authors.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Hyperparameter grid search comparing simulated vs. human trajectory lengths, improvement rates, and mutual information. No formal BIC/AIC/BMS comparison reported — models compared qualitatively by whether they could solve the task and match human behavioral patterns.
- **how_model_fit:** simulate-and-compare (hyperparameters tuned via grid search to match human performance metrics; parameters θ updated online within simulation)
- **data_type_fit_to:** choice behavior (button-press timing and patterns)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 32 (11 female, 21 male); Ulm University students; split into 4 groups of 8 (each group: 4 sensors + 4 actors); ages not reported; compensated 40€ (~4 hours)
- **population_category:** undergraduates
- **population_age_range:** 
- **ecological_validity:** Low ecological validity — highly constrained lab task with binary button-press actions, no verbal communication, abstract cursor-steering task with no naturalistic social interaction. However, the hierarchical structure (sensor/actor division of labor) provides some ecological relevance to real-world organizational structures.
- **eligibility_flag:** FLAGGED — borderline on "learning in a social context." The task involves group coordination and joint action, which is social, but the learning itself is primarily about one's own sensorimotor contribution (movement direction). The "social" aspect is that learning occurs in the context of other agents' actions creating noise/disturbance, and information must be transmitted between groups. The computational models describe individual-level Bayesian or bounded-rational learning, not social learning per se. Additionally, this is closer to sensorimotor adaptation/joint action coordination than social learning about social entities. Flag as: "borderline — learning is sensorimotor coordination in a multi-agent context rather than learning about social agents or social information.
- **concerns:** - No formal model comparison metric (BIC, AIC, etc.) — models compared qualitatively by task completion and visual/statistical similarity to human data - Hyperparameters fitted via grid search without cross-validation or out-of-sample testing - Very small sample (N = 32, only 4 independent groups) - No parameter recovery or model recovery analysis - No posterior predictive checks - Age range not reported - Supplementary materials referenced but not accessible in our folder - The "winning" model designation is informal — Thompson sampling is preferred over bounded rationality model primarily because it is a process model (not just descriptive) and generalizes to evolutionary simulations
- **limitations_reported:** Compared to the number of individual neurons in the brain, the number of players in our game is certainly limited, and it would be great in the future to test much larger groups, possibly in an online setting"; "we cannot conclude that there may not be more complex models that would allow for concurrent co-optimization as observed in our experiment"; "Another open question for the future is, whether our setup could generalize to more complex motor coordination tasks and whether groups of humans could solve such tasks beyond simple target reaching
- **limitations_categorized:** sample size; task simplicity; limited generalizability; model space not exhaustive
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Yes
- **wc_rule4:** Partial
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Partial
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - `eligibility_flag`: MEDIUM — borderline social learning; could be classified as sensorimotor joint action coordination rather than social learning - `model_comparison_metric`: LOW — no formal metric; qualitative comparison only - `winning_model`: MEDIUM — no formal "winning" designation; Thompson sampling preferred narratively as process model that generalizes - `social_param`: MEDIUM — no explicit social parameter; the multi-agent credit assignment is handled implicitly - `effect_size`: MEDIUM — only Kendall's τ values reported; no standardized effect sizes (d, r², β) - `sample_size` (age): LOW — ages not reported in main text
- **cannot_find:** - Ages of participants (not reported) - Formal model comparison statistics (BIC, AIC, etc.) - Parameter recovery results - Model recovery / confusion matrix - Code/data repository link (data available "upon request" only) - Supplement content (referenced as available online but not in our folder)
- **other_notes:** The paper mentions supplementary information is available at the DOI but no supplement file was found in our papers folder. The supplementary figures (S1–S3) are referenced for evolutionary simulation details. This paper is primarily about multi-agent sensorimotor coordination and the computational principles enabling hierarchical control — it sits at the boundary between joint action / motor coordination and social learning. The bounded rationality model is explicitly described as "merely a descriptive model and not a process model," making the Thompson sampling model the de facto winning model. The evolutionary simulation extension (varying network architecture) is a theoretical exploration, not fitted to human data.
- **re_extract_flag:** false (full text accessed; supplement not available but flagged)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- rr_tax_mod_multiplayer_live
- spec_context = social
- spec_depth = parametric
- spec_locus = source
- spec_source = social
- spec_target = partly
- tax_domain_C_exchange_interdependence
- tax_mod_active_interaction
- tax_mod_experiential
- tax_mod_multiplayer_live
- tax_model_MB
- tax_model_bayesian
- tax_param_learning_rate
- tax_param_temperature
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_PE_signal
- tax_rr_param_precision
- tax_rr_primary_topic = cooperation
- tax_rr_topic_cooperation
- tax_topic_cooperation
