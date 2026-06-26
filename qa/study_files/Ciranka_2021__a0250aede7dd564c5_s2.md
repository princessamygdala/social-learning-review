# Ciranka (2021)

- **study_id:** `a0250aede7dd564c5_s2`
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
- **study_focus:** Social influence under uncertainty; developmental trajectory of social susceptibility as driven by subjective uncertainty
- **study_focus_short:** Social influence under uncertainty
- **learning_mode_description:** - Learning mode: Integrating social advice into decisions under uncertainty via Bayesian updating   - Learning from:     - Source type (social): other (peer advisor -- real previous participant)     - Source content (social): action/policy (advisor's risky or safe choice)   - Learning about:     - Target type (non-social): world (optimal choice in marble-jar gamble)     - Target content (non-social): outcome (expected utility of risky vs safe option)
- **task_description:** In the "marble task," participants chose between a risky marble jar (variable outcome) and a safe jar (guaranteed 5 points) across 144 trials. Probabilities were either described visually or inferred from a sequence of 9 sample draws (experience-based). In the social condition, participants saw a peer advisor's choice before deciding.
- **task_paradigm:** Risky decision-making
- **players:** Single agent (participant), single advisor (real previous participant matched to be ~20% riskier)
- **n_players:** single agent (1)
- **partner_type:** human (live)
- **stimuli:** Marble jars with colored marbles (proportions indicating probabilities), point/monetary outcomes, peer advisor choices
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Uncertain utility model (Bayesian updating) best described behavior (looic advantage >500 over next best model) - Risk-taking decreased with age (b_age = -53.27, CI = [-92.98, -12.74]) - Subjective uncertainty (sigma) decreased linearly with age across both conditions - Social impact (KL-divergence between solo and social utilities) decreased with age (b_age = -1.36, CI = [-2.19, -0.51]) - No developmental differences in the weight (psi) assigned to social information - Developmental differences in social impact fully explained by developmental differences in uncertainty - Experience-based risks led to greater subjective uncertainty and greater social impact than described risks (b_experience = 0.05, CI = [0.03, 0.07])
- **effect_size:** - b_EV = 0.20, CI = [0.20, 0.21] (effect of expected value on risky choice) - b_experience = -0.14, CI = [-0.24, -0.04] (experience vs description on risk-taking) - b_socialrisk = 0.28, CI = [0.18, 0.39]; b_socialsafe = -0.32, CI = [-0.54, -0.11] - Social impact on age: b_age = -1.36, CI = [-2.19, -0.51] - (All Bayesian posterior means with 95% CIs)
- **learning_from:** Other (real peer advisor); observed risky or safe choice advice
- **learning_about:** World; expected utility of risky option under uncertainty  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Uncertain utility model (Bayesian updating): U = Beta(alpha, beta) * V^rho, where sigma parameterizes uncertainty in the beta distribution; social influence implemented as Bayesian updating of the beta distribution shape parameters by psi_risky / psi_safe; social impact depends on prior uncertainty
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** 1. {"name": "Uncertain Utility (Bayesian social updating)", "family": "Bayesian belief updating + utility", "n_params": 5, "metric": "LOOIC"} 2. {"name": "Reward Sensitivity model", "family": "Expected utility + reward modulation", "n_params": 4, "metric": "LOOIC"} 3. {"name": "Null model (no social effect)", "family": "Expected utility", "n_params": 3, "metric": "LOOIC"} 4. {"name": "Trembling Hand (distraction)", "family": "Expected utility + noise", "n_params": 4, "metric": "LOOIC"}
- **model_mb_mf:** N/A (not RL; Bayesian)
- **model_params:** - rho: reward sensitivity (power function exponent; rho < 1 = risk-averse, rho > 1 = risk-seeking) - sigma_risk: uncertainty parameter for description-based risks - sigma_uncertainty: uncertainty parameter for experience-based risks - psi_risky [S]: weight of risky social information (separate for risk/uncertainty conditions) - psi_safe [S]: weight of safe social information (separate for risk/uncertainty conditions) - (rho decreased with age; sigma decreased with age; psi did not show developmental trends)
- **social_param:** psi_risky and psi_safe -- weight of social information on belief updating. Crucially, the model shows that social *impact* (KL-divergence) depends on the interaction of psi with sigma (uncertainty), such that equal psi values produce greater social impact when uncertainty is higher.
- **social_param_name:** psi_risky
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** LOOIC (approximate leave-one-out information criterion)
- **how_model_fit:** individual-level-fit (hierarchical Bayesian with age-group hyperpriors, fitted via NUTS/Stan with 4 chains, 6000 iterations)
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
- **sample_size:** N=165 (aged 10-26, M=15.82)
- **population_category:** healthy adults
- **population_age_range:** 10–26
- **ecological_validity:** Moderate improvement over typical lottery tasks -- the marble task uses experience-based risk (sampling marbles before deciding) which better captures real-world uncertainty. However, still a lab-based monetary gambling task with a single computer-matched advisor, no real social interaction.
- **eligibility_flag:** Borderline: learning-vs-decision-making. The Bayesian updating model treats social influence as belief updating (a form of learning), but there is no trial-by-trial learning across the experiment -- each trial is an independent decision with social information incorporated via Bayesian updating within that trial. The "learning" is about how social information changes beliefs within a single decision, not about learning from outcomes over time.
- **concerns:** - Borderline on learning-over-time criterion -- Bayesian updating is within-trial, not across-trial learning - Advisor identity/presence not manipulated - No feedback about choice outcomes (no trial-by-trial learning) - Experience-based condition controls for learning confounds but removes agency (subjects cannot explore) - Chapter described as "in preparation" -- not yet peer-reviewed at time of dissertation defense (2021) - Preregistered hypotheses H1, H3, H5 not confirmed
- **limitations_reported:** Did not manipulate advisor identity or presence; did not manipulate peer observation; gave subjects no agency over their experiences; different real-life risks tap into different uncertainties requiring different cognitive processes; unknown which uncertainties impact adolescents' real-world risk-taking vulnerability
- **limitations_categorized:** Limited ecological validity; no manipulation of social source identity; task simplicity; limited generalizability; no agency/exploration
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 8.5
- **wc_total:** 8.5

## Context flags
- **ctx_copresence:** yes
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
- rr_tax_mod_social_info_search
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- tax_domain_A_influence_transmission
- tax_domain_G_uncertainty_volatility
- tax_mod_action_observation
- tax_mod_social_info_search
- tax_model_bayesian
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = social_uncertainty
- tax_rr_topic_social_info_use
- tax_rr_topic_social_uncertainty
- tax_social_nonsocial_comparison
- tax_topic_social_info_use
- tax_topic_social_uncertainty
