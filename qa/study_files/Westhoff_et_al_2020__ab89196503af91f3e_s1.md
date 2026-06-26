# Westhoff et al. (2020)

- **study_id:** `ab89196503af91f3e_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Westhoff, B., Molleman, L., Viding, E., van den Bos, W., & van Duijvenvoorde, A. C. K. (2020). Developmental asymmetries in learning to adjust to cooperative and uncooperative environments. *Scientific Reports*, *10*, 21761. https://doi.org/10.1038/s41598-020-78546-1
- **citation_short:** Westhoff et al. (2020)
- **doi:** 10.1038/s41598-020-78546-1
- **publication_type:** peer-reviewed journal
- **year:** 2020.0
- **field_of_study:** Behavioural economics / Economics
- **affiliations_raw:** Institute of Psychology, Leiden University, Leiden, The Netherlands; Department of Psychology, University of Amsterdam, Amsterdam, The; University of Amsterdam, Amsterdam, The Netherlands; Institute for Human Development, Berlin, Germany; University College London, London, UK; Center for Adaptive Rationality,; Institute for Brain and; etherlands; emails: b.westhoff@fsw.leidenuniv.nl
- **code_url:** 

## Computational level
- **study_focus:** Cooperation learning / trust learning -- developmental changes in learning to adjust to cooperative and uncooperative social environments, and the roles of social preferences (inequality aversion), prior expectations, and expectation updating.
- **study_focus_short:** Cooperation learning / trust learning -- developmental changes in learning to
- **learning_mode_description:** - Learning mode: Learning from others' cooperative/uncooperative choices about the trustworthiness and cooperativeness of different social environments   - Learning from:     - Source type (social): other (anonymous age-matched peers from two environments)     - Source content (social): action/policy (choice X or Y by interaction partners)   - Learning about:     - Target type (social): group (social environment -- Trustworthy vs. Untrustworthy; Friendly vs. Unfriendly)     - Target content (social): state (mental state; cooperativeness/trustworthiness of the environment)
- **task_description:** Participants (ages 8-23) played repeated one-shot economic games (Trust Game, Coordination Game) with anonymous age-matched peers from two probabilistic social environments (73% vs. 27% cooperative). In each trial, participants chose between two options (A or B), then saw the other player's choice and the monetary outcome for both.
- **task_paradigm:** Trust game
- **players:** Single agent (participant), multi-target (anonymous age-matched peers from two social environments, 15 per environment)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract payoff matrices (dot representations of points), color-coded environment indicators for other players
- **method:** online / behavioural
- **method_full:** Behavioural (online economic games administered in school/university settings)
- **main_result:** - Developmental asymmetry: cooperative adjustment (trusting Trustworthy others) improved markedly across adolescence (Trust Game environment x age linear: B = -0.307, OR = 0.74, 95% CI [0.62, 0.87]); uncooperative adjustment was relatively stable - Coordination Game: environment x age linear interaction (B = -0.458, OR = 0.63, 95% CI [0.53, 0.76]) - Disadvantageous inequality aversion decreased with age (beta = -0.308, 95% CI [-0.139, -0.057]) - Mediation: age-related decrease in disadvantageous inequality aversion partly mediated improvement in cooperative adjustment (Trust Game indirect effect = 0.057, SE = 0.026, 95% CI [0.011, 0.113]; Coordination Game indirect effect = 0.042, SE = 0.020, 95% CI [0.005, 0.083]) - Computational model with social preferences and decaying learning rates best fit data (lowest BIC in both games) - Older cohorts showed stronger decay in learning rates (expectations stabilized earlier); youngest cohort (8-11) showed near-constant learning rates
- **effect_size:** - Developmental asymmetry: cooperative adjustment (trusting Trustworthy others) improved markedly across adolescence (Trust Game environment x age linear: B = -0.307, OR = 0.74, 95% CI [0.62, 0.87]); uncooperative adjustment was relatively stable - Coordination Game: environment x age linear interaction (B = -0.458, OR = 0.63, 95% CI [0.53, 0.76]) - Disadvantageous inequality aversion decreased with age (beta = -0.308, 95% CI [-0.139, -0.057]) - Mediation: age-related decrease in disadvantageous inequality aversion partly mediated improvement in cooperative adjustment (Trust Game indirect effect = 0.057, SE = 0.026, 95% CI [0.011, 0.113]; Coordination Game indirect effect = 0.042, SE = 0.020, 95% CI [0.005, 0.083]) - Computational model with social preferences and decaying learning rates best fit data (lowest BIC in both games) - Older cohorts showed stronger decay in learning rates (expectations stabilized earlier); youngest cohort (8-11) showed near-constant learning rates
- **learning_from:** Other (anonymous peers); their cooperative/uncooperative choices (X or Y) in economic games
- **learning_about:** Group; cooperativeness/trustworthiness of two social environments  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** RL with social preferences (Fehr-Schmidt inequality aversion) and decaying learning rates: p_{t+1} = p_t + lambda_t * PE; lambda_t = lambda_0 * r^{-tau}; choice via softmax with subjective payoffs incorporating alpha (disadvantageous IA) and beta (advantageous IA). Free parameters: lambda_0, tau, theta (decision sensitivity). Social preferences (alpha, beta) fixed at cohort means.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "Basic RL", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BIC"} -- parameters: lambda, theta 2. {"name": "RL + decay", "family": "Rescorla-Wagner", "n_params": 3, "metric": "BIC"} -- parameters: lambda_0, tau, theta 3. {"name": "RL + social preferences (SP)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BIC"} -- parameters: lambda, theta (SP fixed at cohort means) 4. {"name": "RL + SP + decay", "family": "Rescorla-Wagner", "n_params": 3, "metric": "BIC"} -- parameters: lambda_0, tau, theta (SP fixed at cohort means)
- **model_mb_mf:** MF
- **model_params:** - lambda_0: initial learning rate (bounded 0-1) -- Trust Game values by cohort: 8-11: 0.12, 12-14: 0.82, 15-18: 1.00, 19-23: 0.96; Coordination Game: 8-11: 0.67, 12-14: 0.61, 15-18: 1.00, 19-23: 1.00 - tau: decay rate for learning rate (bounded 0-5) -- Trust Game: 8-11: 0.00, 12-14: 1.27, 15-18: 5.00, 19-23: 5.00; Coordination Game: 8-11: 1.94, 12-14: 1.31, 15-18: 5.00, 19-23: 5.00 - theta: decision sensitivity (bounded 0-5) -- Trust Game: 8-11: 0.15, 12-14: 0.12, 15-18: 0.23, 19-23: 0.24; Coordination Game: 8-11: 0.63, 12-14: 0.46, 15-18: 0.53, 19-23: 0.69 - alpha [S]: disadvantageous inequality aversion (transformed from UG indifference points, fixed at cohort mean) - beta [S]: advantageous inequality aversion (transformed from DG indifference points, fixed at cohort mean; Coordination Game only) - prior: initial expectation p_0 (fixed at cohort mean prior)
- **social_param:** alpha (disadvantageous inequality aversion) and beta (advantageous inequality aversion) -- Fehr-Schmidt social preference parameters that modulate the subjective valuation of payoffs, capturing how much participants weight unequal outcomes. These are measured externally (UG, DG) and fixed in the RL model, not freely estimated.
- **social_param_name:** alpha
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (summed across age cohorts)
- **how_model_fit:** Group-level fit (data pooled per age cohort; MLE)
- **data_type_fit_to:** Choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 245 (ages 8-23; 4 cohorts: 8-11 n=54, 12-14 n=73, 15-18 n=57, 19-23 n=61; 58.4% female). Trust Game N=244 (1 excluded for missing disadvantageous IA). Coordination Game N=202 (43 excluded for missing advantageous IA from DG).
- **population_category:** children
- **population_age_range:** 8–23
- **ecological_validity:** Uses incentivized economic games with real consequences for both players (pre-recorded choices from actual age-matched peers), which is more ecologically valid than hypothetical scenarios. However, the controlled social environments are less complex than real-life social interactions (no reputation, social status, culture effects). One-shot interactions rather than repeated interactions with the same partner.
- **eligibility_flag:** 
- **concerns:** - Models fitted at cohort level (pooled data) rather than individual level due to limited number of trials; sensitivity analyses reportedly confirmed consistency but individual-level parameter estimates not reported - Social preference parameters (alpha, beta) fixed at cohort means rather than individually estimated in the RL model - Cross-sectional design; developmental interpretations are speculative without longitudinal data - Sex imbalance across cohorts (80.3% female in oldest cohort) - 54 participants excluded from Coordination Game analyses due to inconsistent DG responses
- **limitations_reported:** Cross-sectional design, as longitudinal studies are necessary to identify developmental patterns; controlled social environments are less complex than real-life social interactions; prior expectations were stated rather than revealed preferences; adult participants mainly recruited through university advertisements limiting representativeness; limited number of observations for individual-level model fitting; participants given prior information about different environments rather than needing to discover base rates independently
- **limitations_categorized:** Cross-sectional design; limited ecological validity; task simplicity; measurement validity (stated vs. revealed preferences); limited generalizability (sampling bias); limited data for individual-level fitting
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Partial
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 9.0
- **wc_total:** 9.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_params confidence: HIGH for parameter values (Table S7); MEDIUM for social preference parameter values (alpha, beta transformed values shown in Figure S4 but exact cohort means not tabulated) - wc_5 (parameter recovery): MEDIUM -- supplement describes model recovery (correct model identified) but does not clearly report parameter-level recovery (generating vs. recovered parameter correlations)
- **cannot_find:** Exact cohort-mean values of transformed alpha and beta used in RL models (Figure S4 shows distributions but exact values not tabulated)
- **other_notes:** The study also includes a non-social learning task (computer opponents) analyzed with the same RL framework (supplement), which provides a useful within-study comparison. The paper uses the Fehr & Schmidt (1999) inequality aversion framework integrated into RL, which is a notable modeling contribution for social learning. Data and code are openly available.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_children
- pop_healthy_adults
- rr_pop_adolescents
- rr_pop_children
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = structural
- spec_locus = source+target+context
- spec_source = social
- spec_target = social
- tax_domain_C_exchange_interdependence
- tax_mod_action_observation
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_primary_topic = trust
- tax_rr_secondary_topic = cooperation
- tax_rr_topic_cooperation
- tax_rr_topic_trust
- tax_social_nonsocial_comparison
- tax_topic_cooperation
- tax_topic_trust
