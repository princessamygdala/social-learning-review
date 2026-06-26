# Oguchi et al. (2023)

- **study_id:** `ac6e6ff32b9164bef_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Oguchi, M., Li, Y., Matsumoto, Y., Kiyonari, T., Yamamoto, K., Sugiura, S., & Sakagami, M. (2023). Proselfs depend more on model-based than model-free learning in a non-social probabilistic state-transition task. *Scientific Reports*, *13*, 1419. https://doi.org/10.1038/s41598-023-27609-0
- **citation_short:** Oguchi et al. (2023)
- **doi:** 10.1038/s41598-023-27609-0
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Psychology
- **affiliations_raw:** Institute, Tamagawa University, 6-1-1, Tamagawagakuen, Machida, Tokyo, Japan; ether to prioritize self‑interest or respect for others—proself or prosocial; School of Social Informatics, Aoyama Gakuin University, Kanagawa,; Department of Psychology, Faculty of Human Sciences,; University, Fukuoka, Japan; University, Nagoya, Japan; Institute, Aichi, Japan; School; emails: sakagami@lab.tamagawa.ac.jp
- **code_url:** 

## Computational level
- **study_focus:** Relationship between social value orientation (proself vs. prosocial) and model-based/model-free reinforcement learning dependence; social dual-process theory from a learning perspective.
- **study_focus_short:** Relationship between social value orientation (proself vs. prosocial) and
- **learning_mode_description:** - Learning mode: Learning from probabilistic state-transition outcomes about state-action values, with individual differences in MB/MF balance linked to social value orientation.   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (monetary rewards from state transitions)   - Learning about:     - Target type (non-social): world (task state-transition structure and state-action values)     - Target content (non-social): state (world state; state-transition probabilities and reward contingencies)
- **task_description:** Participants performed a sequential two-choice Markov decision task with probabilistic state transitions (70%/30%) across three stages, earning monetary rewards (0, 10, or 25 yen) at the final stage over 200 trials. Social value orientation was separately measured using the SVO Slider Measure.
- **task_paradigm:** Two-step task
- **players:** Single agent (participant), no social interaction during the task; SVO measured separately with hypothetical anonymous partner.
- **n_players:** single agent (1)
- **partner_type:** unclear
- **stimuli:** Geometric figures (one per state), monetary outcomes (0, 10, 25 yen), SVO Slider Measure items.
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - Proselfs had greater model-based dependence (weight w) than prosocials in block 1 (z = 2.19, p = 0.037, Wilcoxon rank-sum post-hoc)   - Main effect of social preference on weight w (F[1,82] = 8.96, p = 0.0037, ANOVA)   - Interaction between social preference and block for w in first 80 trials (F[1,79] = 7.37, p = 0.008)   - Proselfs distinguished common/rare transitions from block 1; prosocials only from block 3   - Simulation: model-based learner had greater learning speed than model-free (z = 17.02, p = 6.45 x 10^-65, Wilcoxon rank-sum)   - GLME for w: SVO effect marginal (estimate = -5.23 x 10^-3, t = -1.78, p = 0.075)
- **effect_size:** MEDIUM — no standardized effect sizes (d, eta-squared) for key group comparison; only F and z values reported.
- **learning_from:** Self; reward outcomes from probabilistic state transitions in a non-social task.
- **learning_about:** World; state-transition probabilities and state-action values in a Markov decision task.  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** HYBRID learner (w * Q_FWD + (1-w) * Q_SARSA; 4 params: alpha, eta, beta, w)
- **model_family:** MB/MF hybrid
- **model_class:** PE learning
- **all_models_tested:** - {"name": "SARSA (model-free)", "family": "SARSA/TD learning", "n_params": 2, "metric": "BIC"} - {"name": "FORWARD (model-based)", "family": "Forward model-based RL", "n_params": 2, "metric": "BIC"} - {"name": "HYBRID", "family": "Hybrid MB/MF RL", "n_params": 4, "metric": "BIC"}
- **model_mb_mf:** MB/MF hybrid
- **model_params:** - alpha (model-free learning rate): controls TD update strength. Proself mean (200 trials): 0.34 +/- 0.04; Prosocial: 0.33 +/- 0.04 - eta (model-based learning rate): controls state prediction error update. Proself: 0.49 +/- 0.03; Prosocial: 0.48 +/- 0.03 - beta (inverse temperature): controls exploration-exploitation. Proself: 5.21 +/- 0.48; Prosocial: 4.58 +/- 0.55 - w (weight): balance between MB and MF (1 = pure MB, 0 = pure MF). Proself: 0.49 +/- 0.05; Prosocial: 0.40 +/- 0.06. [S] — key social-relevant parameter, as its variation is associated with SVO group differences.
- **social_param:** LOW — w is not a social parameter in the model; it is the parameter whose variation correlates with a social trait.  ## CANNOT FIND  - Standardized effect sizes (Cohen's d, eta-squared) for the proself vs. prosocial comparison on model parameters - Formal parameter recovery or model recovery results - Any preregistration information  ## OTHER NOTES  This paper tests a theoretical link (the "learning approach" in social dual-process theory) between domain-general MB/MF reinforcement learning and social value orientation. The computational modeling is applied entirely to a non-social task. The social dimension enters only as an individual-difference correlate (SVO scores). This is a strong candidate for flagging as not meeting the "learning occurs in a social context" criterion, though it us
- **social_param_name:** w
- **social_param_value:** 0.49
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (Bayesian Information Criterion)
- **how_model_fit:** individual-level-fit (MAP estimation per participant per block of 40 trials); also validated with fixed-effects (group-level) analysis
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A (no neuroimaging)  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 183 (1 excluded from 184; 92 females, 1 no-answer; ages 18-36, mean 21.20 +/- 1.67 SD). Proself group: n = 46 (SVO < 7.82 degrees); Prosocial group: n = 35 (SVO > 37.48 degrees). Complementary analysis: Proself n = 66, Prosocial n = 117 (cutoff at 22.45 degrees).
- **population_category:** healthy adults
- **population_age_range:** 18–36
- **ecological_validity:** Low. The task is an abstract, non-social probabilistic state-transition task conducted online. SVO was measured separately with hypothetical (not real) allocation decisions. No real social interaction during the learning task. The link between non-social MB/MF learning and social preferences is correlational, not tested in a social context.
- **eligibility_flag:** LOW confidence that this meets inclusion criteria — the task is non-social; SVO is a separate individual-difference measure only.
- **concerns:** - The core learning task is entirely non-social — the paper examines correlations between non-social learning parameters and a social trait (SVO), not social learning per se. - No effect sizes (Cohen's d, eta-squared) reported for the key group comparison on w; only F-statistics and p-values. - The significant difference in w between proself and prosocial was found only when using extreme SVO cutoffs (7.82 and 37.48 degrees), not the conventional 22.45 degree cutoff, reducing generalizability. - Online experiment with potential RT measurement noise. - No parameter recovery or model recovery analysis reported. - Correlation between parameters in later blocks raises identifiability concerns.
- **limitations_reported:** Since this experiment was conducted as an online experiment, the measurement of the reaction time may not be accurate"; systematic errors up to 30 ms depending on OS and browser (jsPsych); did not control for participants' experimental environment; "no definitive claims can be made regarding the causal relationship between the two" (MB/MF and SVO); university students in one country — did not examine or control for environmental heterogeneity; model-free strategies may masquerade as model-based with extensive training; mixing vs. switching between MB/MF is unresolved.
- **limitations_categorized:** Limited ecological validity; online measurement noise; correlational design (no causal claims); limited generalizability (single country, university students); task simplicity; model identifiability concerns.  ---  ## WC CHECKLIST (Wilson & Collins, 2019)  1. **Design a good experiment**: Yes — task specifically designed to dissociate MB/MF learning (sequential two-choice Markov decision task from Glascher et al., 2010). 2. **Design good models**: Yes — three competing models tested (SARSA, FORWARD, HYBRID). 3. **Simulate, simulate, simulate**: Partial — simulations conducted post-hoc to confirm consistency with behavioral results (model-based vs. model-free learners simulated), but no pre-fitting simulation to verify task identifiability. 4. **Fit the parameters**: Yes — MAP estimation (individual-level) and fixed-effects analysis. 5. **Check parameter recovery**: No — no parameter recovery analysis reported. 6. **Check model recovery**: No — no model recovery / confusion matrix reported. 7. **Fit real data and compare models**: Yes — BIC comparison across three models; HYBRID best for all blocks. 8. **Validate the winning model**: Partial — simulations using estimated parameters replicated behavioral patterns (reward gain, learning speed), but no formal posterior predictive check. 9. **Analyze the winning model**: Yes — latent parameters (especially w) analyzed across groups and blocks; correlations between parameters examined. 10. **Report results transparently**: Yes — data and MATLAB code available on OSF (https://osf.io/hvjce/).
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
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = general
- spec_locus = source+target+context
- spec_source = social
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_model_MB
- tax_model_MB_MF_hybrid
- tax_model_rescorla_wagner
- tax_param_MB_MF_balance
- tax_param_learning_rate
- tax_param_temperature
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
