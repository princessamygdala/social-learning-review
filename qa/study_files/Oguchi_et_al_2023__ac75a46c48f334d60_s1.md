# Oguchi et al. (2023)

- **study_id:** `ac75a46c48f334d60_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Oguchi, M., Li, Y., Matsumoto, Y., Kiyonari, T., Yamamoto, K., Sugiura, S., & Sakagami, M. (2023). Proselfs depend more on model-based than model-free learning in a non-social probabilistic state-transition task. *Scientific Reports*, 13, 1419. https://doi.org/10.1038/s41598-023-27609-0
- **citation_short:** Oguchi et al. (2023)
- **doi:** 10.1038/s41598-023-27609-0
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Psychology
- **affiliations_raw:** Institute, Tamagawa University, 6-1-1, Tamagawagakuen, Machida, Tokyo, Japan; ether to prioritize self‑interest or respect for others—proself or prosocial; School of Social Informatics, Aoyama Gakuin University, Kanagawa,; Department of Psychology, Faculty of Human Sciences,; University, Fukuoka, Japan; University, Nagoya, Japan; Institute, Aichi, Japan; School; emails: sakagami@lab.tamagawa.ac.jp
- **code_url:** 

## Computational level
- **study_focus:** Social value orientation and model-based/model-free reinforcement learning; relationship between individual differences in social preferences (proself vs. prosocial) and domain-general learning mechanisms
- **study_focus_short:** Social value orientation and model-based/model-free reinforcement learning
- **learning_mode_description:** - Learning mode: Learning from one's own reward outcomes in a non-social state-transition task, with individual differences in learning strategy (MB vs. MF) correlated with social value orientation measured separately.   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (monetary reward from state transitions)   - Learning about:     - Target type (non-social): world (state-transition structure and reward contingencies)     - Target content (non-social): state (state-action values / transition probabilities)
- **task_description:** Participants performed a sequential two-choice Markov decision task (200 trials) with a two-layer tree structure where first- and second-stage choices led probabilistically (70%/30%) to outcome states associated with monetary rewards (0, 10, or 25 yen). Social value orientation was measured separately using the SVO Slider Measure.
- **task_paradigm:** Two-step task
- **players:** Single agent (participant), no social partner in task; SVO measured via separate allocation task with anonymous other
- **n_players:** single agent (1)
- **partner_type:** none
- **stimuli:** Geometric figures (abstract), monetary outcomes (0/10/25 yen)
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Proself group showed greater model-based dependence (weight w) than prosocial group, especially in the early phase of the session (Block 1: z = 2.19, p = 0.037, Wilcoxon rank-sum test) - Main effect of social preference on weight w (F[1,82] = 8.96, p = 0.0037) - Interaction between social preference and block for w in first 80 trials (F[1,79] = 7.37, p = 0.008) - Proself group earned greater reward in early trials (significant at trials #11, #12, #73) - Proself group distinguished common vs. rare transitions from Block 1; prosocial group only from Block 3 onward - GLME: marginal effect of SVO on w (estimate = -5.23 x 10^-3, t = -1.78, p = 0.075) - Simulation: model-based learner learned state-action values faster than model-free (slope comparison: z = 17.02, p = 6.45 x 10^-65)
- **effect_size:** - Weight w: ANOVA main effect of social preference F[1,82] = 8.96, p = 0.0037 - Weight w interaction (first 80 trials): F[1,79] = 7.37, p = 0.008 - Block 1 w comparison: z = 2.19, p = 0.037 - Simulation slope comparison: z = 17.02, p = 6.45 x 10^-65 - (Note: No Cohen's d, r, or other standardized effect sizes reported)
- **learning_from:** Self; reward outcomes in non-social state-transition task
- **learning_about:** World; state-action values and transition probabilities in a Markov decision task  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** HYBRID (SARSA + FORWARD; 4 params: α [MF learning rate], η [MB learning rate], β [inverse temperature], w [MB/MF weight])
- **model_family:** MB/MF hybrid
- **model_class:** PE learning
- **all_models_tested:** - {"name": "SARSA (model-free)", "family": "SARSA/TD learning", "n_params": 2, "metric": "BIC"} - {"name": "FORWARD (model-based)", "family": "Model-based RL (forward planning)", "n_params": 2, "metric": "BIC"} - {"name": "HYBRID (SARSA + FORWARD)", "family": "Hybrid MB/MF RL", "n_params": 4, "metric": "BIC"}
- **model_mb_mf:** MB/MF hybrid
- **model_params:** - α (model-free learning rate): controls update strength of SARSA learner. Proself: 0.34 +/- 0.04; Prosocial: 0.33 +/- 0.04 (200-trial fit) - η (model-based learning rate): controls update strength of transition probability estimates in FORWARD learner. Proself: 0.49 +/- 0.03; Prosocial: 0.48 +/- 0.03 - β (inverse temperature): controls action selection stochasticity via softmax. Proself: 5.21 +/- 0.48; Prosocial: 4.58 +/- 0.55 - w [S] (weight): mixing parameter for MB vs. MF (1 = pure MB, 0 = pure MF). Proself: 0.49 +/- 0.05; Prosocial: 0.40 +/- 0.06 - γ (discount factor): fixed at 1
- **social_param:** w (weight) -- the MB/MF mixing parameter. Higher w indicates greater model-based dependence. Proselfs had significantly higher w than prosocials in early learning blocks, linking social value orientation to the balance of learning systems.
- **social_param_name:** w
- **social_param_value:** 0.49
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (Bayesian Information Criterion)
- **how_model_fit:** individual-level-fit (MAP estimation per participant per 40-trial block); also validated with fixed-effects analysis (group-level)
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
- **sample_size:** N = 183 (1 excluded from 184 for missing data); proself group n = 46 (SVO < 7.82 degrees), prosocial group n = 35 (SVO > 37.48 degrees); ages 18-36 (M = 21.20, SD = 1.67); 92 females, 1 no-answer
- **population_category:** healthy adults
- **population_age_range:** 18–36
- **ecological_validity:** Low -- abstract geometric figures in an online Markov decision task with monetary rewards; social value orientation measured via hypothetical resource allocation (SVO Slider) with no real incentive; no actual social interaction during the learning task itself; online experiment with uncontrolled participant environment
- **eligibility_flag:** The learning task itself is NON-SOCIAL (a standard probabilistic state-transition task). The social component is limited to an individual difference measure (SVO) used to group participants. The paper does not involve learning in a social context -- it examines how a pre-existing social preference trait correlates with non-social learning strategy. FLAG: The task does not involve social learning; learning does not occur in a social context. The social element (SVO) is a between-subjects moderator, not part of the learning process.
- **concerns:** - The task is entirely non-social; SVO is measured separately and used only as a grouping variable - No standardized effect sizes (Cohen's d, r, etc.) reported for the key group comparisons - The proself/prosocial groups used stringent thresholds (7.82 degrees / 37.48 degrees), excluding ~56% of participants from the primary comparison; when using the conventional 22.45 degree threshold, group differences in model parameters were NOT significant (Supplementary Fig. 4) - Online experiment with potential RT measurement noise (acknowledged by authors) - Individual-level MAP estimation on 40-trial blocks may have low reliability due to small trial counts - No parameter recovery analysis performed - No model recovery analysis performed - γ fixed at 1 without justification beyond stating the task does not involve temporal delays
- **limitations_reported:** Online experiment may introduce systematic RT errors up to 30 ms depending on OS and browser; no control over participant experimental environment; cannot definitively establish causal relationship between MB/MF learning dependence and SVO; study conducted with university students in one country, environmental heterogeneity not examined or controlled for; possible that proselfs were more strongly motivated by monetary rewards than prosocials; model-free strategies could potentially masquerade as model-based with extensive training
- **limitations_categorized:** limited ecological validity; no causal inference; limited generalizability (single country, university sample); potential confound (motivation); online measurement noise; task simplicity
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
- **wc_rule10:** Yes
- **wc_score:** 7.0
- **wc_total:** 7.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - effect_size: LOW -- no standardized effect sizes reported; only F-statistics, z-values, and p-values available - social_param: MEDIUM -- w is not inherently a "social" parameter; it becomes socially relevant only through between-group comparison by SVO - eligibility_flag: HIGH -- the task is non-social; this is a clear flag
- **cannot_find:** - Standardized effect sizes (Cohen's d, η², etc.) for key comparisons - Exact BIC values for each model (mentioned as computed but only shown in figure, not reported numerically) - n_params for SARSA and FORWARD not explicitly stated (inferred: SARSA has α, β = 2 params; FORWARD has η, β = 2 params)
- **other_notes:** This paper examines the correlation between social value orientation (a trait measured separately) and the balance of model-based vs. model-free learning in a non-social task. It does NOT study social learning per se. The "social" component is entirely a between-subjects individual difference variable (SVO), not part of the task or learning environment. The paper's theoretical contribution is to the "social dual-process theory" by showing that proselfs rely more on model-based learning generally, but the learning itself is domain-general and non-social. The supplementary analyses using the conventional SVO cutoff (22.45 degrees) showed NO significant group differences in model parameters, suggesting the finding is specific to extreme SVO groups.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_model_MB
- tax_model_MB_MF_hybrid
- tax_model_rescorla_wagner
- tax_param_MB_MF_balance
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_MB_MF_hybrid
- tax_rr_model_family = MB_MF_hybrid
- tax_rr_param_MB_MF_balance
- tax_rr_primary_topic = cooperation
- tax_rr_topic_cooperation
- tax_social_nonsocial_comparison
- tax_topic_cooperation
