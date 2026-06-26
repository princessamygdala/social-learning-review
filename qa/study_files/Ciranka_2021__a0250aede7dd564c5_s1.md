# Ciranka (2021)

- **study_id:** `a0250aede7dd564c5_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Ciranka, S. (2021). *Computational mechanisms of social influence during adolescence* [Doctoral dissertation, Freie Universitat Berlin]. ProQuest Dissertations Publishing. ProQuest Number: 29175547.
- **citation_short:** Ciranka (2021)
- **doi:** 10.3389/fpsyg.2019.01915
- **publication_type:** thesis
- **year:** 2021.0
- **field_of_study:** Psychology
- **affiliations_raw:** 
- **code_url:** 

## Computational level
- **study_focus:** Social influence on adolescent risk-taking; formalizing verbal models of peer influence (social motivation, reward sensitivity, distraction) as expected utility models
- **study_focus_short:** Social influence on adolescent risk-taking
- **learning_mode_description:** - Learning mode: Integrating social information (peer choices) into own risky decisions   - Learning from:     - Source type (social): other (peer / computer-generated agent)     - Source content (social): action/policy (observed risky or safe choices)   - Learning about:     - Target type (non-social): world (optimal choice in lottery)     - Target content (non-social): outcome (expected utility of risky vs safe option)
- **task_description:** Participants chose between a risky gamble and a safe option on repeated trials. On some trials, they observed a virtual peer's choice before deciding. The task varied expected values and probabilities across trials.
- **task_paradigm:** Risky decision-making
- **players:** Single agent (participant), single social source (virtual peer/computer agent). Reanalysis of two published datasets: Blankenstein et al. (2016) and Braams et al. (2019).
- **n_players:** single agent (1)
- **partner_type:** computer (algorithmic)
- **stimuli:** Wheels of fortune / colored bars (lottery representations), monetary outcomes, virtual peer choices
- **method:** behavioural
- **method_full:** behavioural (reanalysis of existing datasets)
- **main_result:** - Asymmetric social influence model best fit data in both experiments (DIC comparison) - Safe social information had stronger influence than risky social information across all age groups - Impact of risky social information strongest in youngest participants and decreased with age (Exp 1: beta_AgeLin = -1.5, CI = [-1.9, -1.2]) - Adolescents used safe social information more during adolescence (Exp 2: beta_AgeQuad for safe = 0.6, CI = [0.4, 0.8]) - Model and parameter recovery confirmed distinguishability of all models
- **effect_size:** - Exp 1 (Blankenstein): beta_AgeLin for risky advice = -1.5, CI = [-1.9, -1.2]; beta_AgeLin for safe advice = 1.4, CI = [0.9, 2.0]; beta_AgeQuad for risky = -0.6, CI = [-0.9, -0.2] - Exp 2 (Braams): beta_AgeQuad for risky = -0.5, CI = [-0.7, -0.3]; beta_AgeQuad for safe = 0.6, CI = [0.4, 0.8] - (All are Bayesian posterior means with 95% credible intervals, not traditional effect sizes)
- **learning_from:** Other (virtual peer); observed risky or safe choices
- **learning_about:** World; optimal choice strategy in monetary lotteries  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Asymmetric social influence model: EU = p * V^rho + psi_risky (if social signal = risky) or + psi_safe (if social signal = safe); with separate psi parameters for risky and safe social information, rho for reward sensitivity, tau for choice temperature
- **model_family:** Utility / EV
- **model_class:** Utility maximization
- **all_models_tested:** 1. {"name": "Standard Expected Utility (null)", "family": "Expected utility", "n_params": 2, "metric": "DIC"} 2. {"name": "Symmetric Social Influence", "family": "Expected utility + social", "n_params": 3, "metric": "DIC"} 3. {"name": "Asymmetric Social Influence", "family": "Expected utility + social", "n_params": 4, "metric": "DIC"} 4. {"name": "Reward Sensitivity", "family": "Expected utility + reward modulation", "n_params": 3, "metric": "DIC"} 5. {"name": "Social Distraction", "family": "Expected utility + trembling hand", "n_params": 3, "metric": "DIC"}
- **model_mb_mf:** N/A (not RL)
- **model_params:** - rho: reward sensitivity (curvature of utility function) - tau: choice temperature / sensitivity - psi_risky [S]: social influence parameter for risky social information - psi_safe [S]: social influence parameter for safe social information - (No mean fitted values reported in the text)
- **social_param:** psi_risky and psi_safe -- capture the asymmetric impact of observing risky versus safe peer choices on subjective utility
- **social_param_name:** psi_risky
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** DIC (Deviance Information Criterion)
- **how_model_fit:** individual-level-fit (hierarchical Bayesian with group-level hyperparameters, fitted via NUTS/Stan)
- **data_type_fit_to:** choice behavior  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Exp 1: n=157 (aged 10-26, from Blankenstein et al., 2016); Exp 2: n=99 (aged 12-22, from Braams et al., 2019). Simulation: 5 x 12 x 50 = 3000 simulated agents.
- **population_category:** healthy adults
- **population_age_range:** 10–26
- **ecological_validity:** Limited; uses monetary lottery choices with described probabilities; social information is from a virtual/computer agent, not real peers. No real social interaction. However, reanalysis of data from two independent labs adds some generalizability.
- **eligibility_flag:** Borderline: learning-vs-decision-making. Models are expected utility models for single decisions, not learning models. No trial-by-trial updating or learning over time. Social information influences single choices rather than being integrated into a learning process. Also, this is a reanalysis of previously published data.
- **concerns:** - Reanalysis of existing data, not original data collection - Expected utility models, not learning models -- borderline inclusion - Social information from virtual/computer agent, not actual peers - Ambiguous trials excluded from main analysis (supplementary analysis confirms same results) - The two reanalyzed datasets use different stimuli and paradigms, though results converge
- **limitations_reported:** Results only apply to paradigms where people observe behavior; cannot generalize to being-observed paradigms; real-life decisions are more complex than binary choices; did not model ambiguity in main analysis; models do not capture affective content of social contexts; current framework limited to expected utility and does not include learning dynamics
- **limitations_categorized:** Limited ecological validity; limited generalizability; task simplicity; no learning dynamics modeled; affect not captured
- **preregistered:** No
- **wc_rule1:** Partial
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 9.5
- **wc_total:** 9.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `eligibility_flag`: Both Studies 1 and 2 are borderline learning-vs-decision-making (MEDIUM confidence) - `cannot_find`: No DOI for the dissertation itself; Chapter 3 DOI unavailable (in preparation); no mean fitted parameter values reported for Study 1 - Study 1 effect sizes are Bayesian credible intervals, not traditional effect size measures (MEDIUM confidence in comparability)
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false (full text available and read in entirety)

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_healthy_adults
- rr_pop_adolescents
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- spec_context = partly
- spec_depth = structural
- spec_locus = source
- spec_source = social
- spec_target = partly
- tax_domain_A_influence_transmission
- tax_mod_action_observation
- tax_model_utility
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = utility_EV
- tax_rr_model_utility_EV
- tax_rr_param_precision
- tax_rr_param_social_bonus
- tax_rr_primary_topic = norm_conformity
- tax_rr_secondary_topic = social_info_use
- tax_rr_topic_norm_conformity
- tax_rr_topic_social_info_use
- tax_topic_norm_conformity
- tax_topic_social_info_use
