# Wadhera & Kakkar (2021)

- **study_id:** `a95587b4f9d0dd433_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Wadhera, T., & Kakkar, D. (2021). Modeling risk perception using independent and social learning: Application to individuals with autism spectrum disorder. *The Journal of Mathematical Sociology*, *45*(4), 223–245. https://doi.org/10.1080/0022250X.2020.1774877
- **citation_short:** Wadhera & Kakkar (2021)
- **doi:** 10.1080/0022250X.2020.1774877
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** mity style toward risk very easily (Knoll, Leung, Foulkes, & Blakemore,; mitated between the peers of the same age-group (Gardner & Steinberg,; Department of Electronics and Communication Engineering, Dr; Institute of Technology, Jalandhar 144011, India; mitation, statistical and observational lear; Department of Electronics and; Institute of; emails: tanu1991libra@gmail.com, tanu.ec.16@nitj.ac.in
- **code_url:** 

## Computational level
- **study_focus:** Risk perception learning through independent and social observational learning in autism spectrum disorder
- **study_focus_short:** Risk perception learning through independent and social observational learning
- **learning_mode_description:** - Learning mode: Learning from observing others' responses (trainer or peer-group) about danger/safety classification of risk-related visual stimuli   - Learning from:     - Source type (social): other (trainer) / group (TD peer-group)     - Source content (social): action/policy (others' classification responses to risk stimuli)   - Learning about:     - Target type (non-social): world (traffic-related risk situations)     - Target content (non-social): state (danger/safety state of the stimulus situation)
- **task_description:** Participants completed a two-alternative forced-choice task in which they classified animated traffic-light images as risky or safe across 120 trials. In a second phase, ASD participants observed the responses of either a trainer or a TD peer-group before re-evaluating their own responses.
- **task_paradigm:** Observational learning task
- **players:** Multi-agent (ASD participants + trainer or TD peer-group as social sources), single-target (risk stimuli). "Single agent (participant), multi-source (trainer or TD peer-group of 50)
- **n_players:** small group (3-4)
- **partner_type:** human (live)
- **stimuli:** Animated traffic-light images depicting risky and safe road situations, binary response (R/S keys)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - ASD participants showed intact but weak risk perception compared to TD (d' ASD = 0.427 vs. d' TD = 1.42; classification accuracy ASD = 51.67% vs. TD = 80.33%)   - RP significantly higher in ASD second phase (after social learning) vs. first phase, under trainer influence (Mean Difference = 0.318, t(49) = 28.43) and peer-group influence (Mean Difference = 0.189, t(49) = 27.71)   - Social influence factor: S_f = 0.3937 (trainer), S_f = 0.3197 (peer-group)   - Priming memory factor: omega = 0.6860 (ASD), omega = 0.4380 (TD)   - Negative correlation between RP and ADOS_SA (r = -0.54) and ADOS_RRB (r = -0.48)   - Positive correlations between RP and BRP subscales (r = 0.52–0.60)
- **effect_size:** - d' ASD = 0.427, d' TD = 1.42 - S_f (trainer) = 0.3937, S_f (peer-group) = 0.3197 - omega (ASD) = 0.6860, omega (TD) = 0.4380 - RMSE (ASD Phase 1) = 0.2263, RMSE (TD Phase 1) = 0.1783 - RMSE (ASD trainer influence) = 0.1738, RMSE (ASD TD influence) = 0.2470 - r(RP_ASD, ADOS_SA) = -0.54; r(RP_ASD, ADOS_RRB) = -0.48 - r(RP_ASD, BRP Risk Assessment) = 0.58; r(RP_ASD, BRP Fear) = 0.52; r(RP_ASD, BRP Peer Admiration) = 0.60; r(RP_ASD, BRP Seriousness) = 0.54
- **learning_from:** Other (trainer) / group (TD peer-group); observing others' classification responses to risk stimuli
- **learning_about:** World; danger/safety state of traffic-related risk situations  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Bayesian risk-perception model: D_n = [p * P_n + (m * B_n + tau) + d * D_{n-1}] / (p + m + d); RP(i) = 1 / [1 + exp(-alpha * D_i + epsilon)]; with social learning: P_n = P^IL_n + S_f * (beta_n - P^IL_n). Key fitted params: omega = 0.6860 (ASD), 0.4380 (TD); S_f = 0.3937 (trainer), 0.3197 (peer); alpha = 0.1, epsilon = 3.
- **model_family:** Bayesian
- **model_class:** PE learning / Belief updating
- **all_models_tested:** [{"name": "Risk-Perception Model (Phase 1, no social learning)", "family": "Bayesian belief updating", "n_params": 7, "metric": "RMSE"}, {"name": "Risk-Perception Model (Phase 2, with social learning)", "family": "Bayesian belief updating", "n_params": 8, "metric": "RMSE"}]  Note: The paper does not test competing models against each other. It uses a single model framework with two phases (with/without the social learning parameter S_f). No formal model comparison was conducted.
- **model_mb_mf:** N/A (not RL; Bayesian belief updating framework)
- **model_params:** - alpha (sigmoid steepness): fixed at 0.1 - epsilon (sigmoid offset): fixed at 3 - omega (priming memory factor) [fitted]: 0.6860 (ASD), 0.4380 (TD) - S_f (social influential factor) [S] [fitted]: 0.3937 (trainer), 0.3197 (peer-group) - beta_n (other person's observed response) [S]: [0, 1] - P^IL_n (independent learning; binary correctness): 0 or 1 - B_n (priming effect): computed from Eq. 5–6 - M_n (dynamic memory parameter): [0, 1], initialized at 0.5 - lambda (repetition/alternation indicator): +1 or -1 - theta (knowledge threshold): fixed at 0.2 - tau (small memorization constant): random in [0, 0.01] - p (individual knowledge weight): 0, 0.5, or 1 (conditional) - m (priming weight): 0 or 1 (conditional) - d (past knowledge weight): 0.5 or 1 (conditional)
- **social_param:** S_f (influential factor) [S] — quantifies the degree to which observing another person's (trainer or peer-group) response influences the individual's own knowledge/response. Range [0, 1]; 0 = no influence, 1 = full influence. Fitted values: 0.3937 (trainer), 0.3197 (peer-group).
- **social_param_name:** S_f
- **social_param_value:** 0.3937
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** RMSE (root mean square error between model-simulated RP and participant experimental RP)
- **how_model_fit:** simulate-and-compare (1000 simulation rounds; best-fit parameter found by minimizing RMSE between model output and participant data)
- **data_type_fit_to:** choice behavior (binary risky/safe classifications across 120 trials)  ---  ### IMPLEMENTATION LEVEL

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
- **sample_size:** N = 100 (50 ASD, aged 8–21 years, M = 13.9, SD = 3.1, male:female = 9:1; 50 TD, aged 8–18 years, M = 11.8, SD = 2.9, male:female = 3:2). Two additional ASD participants excluded for IQ < 70. In Phase 2, ASD group split: 25 observed trainer, 25 observed TD peer-group.
- **population_category:** clinical
- **population_age_range:** 8–21
- **ecological_validity:** Moderate-low. Task uses animated traffic-light images (ecologically relevant to real road risk), but the two-alternative forced-choice format is highly constrained and lab-based. Social learning is one-directional (observing pre-recorded responses), not interactive. The stimuli relate to real-world danger scenarios, which improves ecological relevance somewhat.
- **eligibility_flag:** Borderline — the computational model is a mathematical simulation framework with RMSE-based fitting rather than a standard computational cognitive model with formal parameter estimation. Social learning is present and learning occurs over time (120 trials). Recommend inclusion with flag.
- **concerns:** - No formal model comparison: only one model framework is tested (with/without social learning parameter); no competing model architectures compared - Parameter fitting via RMSE minimization over simulation grid rather than likelihood-based estimation (MLE or Bayesian) - No parameter recovery analysis - No model recovery analysis - No posterior predictive checks - The "Bayesian framework" label is used loosely — the model integrates prior and current knowledge via a weighted average (Eq. 9), but does not use formal Bayesian inference with likelihoods and posterior distributions - alpha and epsilon appear to be hand-selected (alpha = 0.1, epsilon = 3) without systematic fitting - Supplement referenced in text (line 42: "Supplemental data for this article can be accessed on the publisher's website") but not accessible; clinical measures (ADOS-CSS, BRP scale) details stated to be in supplementary material - ASD sample age range (8–21) is very broad
- **limitations_reported:** The model considered only a single direction of influence (positive influence of trainer and peer-group); individuals with low IQ levels were not considered; diversity in IQ and severity of ASD was not factored as covariates; sub-groups within ASD sample not examined; effect of cultural, gender, and age variations was not encountered; behavioral issues of individuals had to be considered before initiating the task; most affected individuals were reluctant requiring additional practice and rewards for participation
- **limitations_categorized:** Unidirectional social influence only; limited sample diversity (IQ exclusion); no subgroup analysis; no demographic covariates (culture, gender, age); task compliance challenges in clinical population; limited generalizability
- **preregistered:** No
- **wc_rule1:** Partial
- **wc_rule2:** No
- **wc_rule3:** Partial
- **wc_rule4:** Partial
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 3.5
- **wc_total:** 3.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `model_family`: MEDIUM confidence — authors call this a "Bayesian framework" but it is a weighted averaging scheme, not formal Bayesian inference - `eligibility_flag`: MEDIUM confidence — borderline computational modeling (simulation-based fitting, not formal likelihood-based) - `all_models_tested`: LOW confidence — the paper does not formally compare models; the two "phases" are the same model with/without S_f - `wc_guidelines` Rule 3: MEDIUM — simulations performed but for fitting, not for a priori model validation
- **cannot_find:** - Supplement content (referenced but not accessible; described as containing ADOS-CSS and BRP scale details) - Formal model comparison results (none conducted) - Parameter recovery results (none conducted) - Confidence intervals or standard errors for fitted omega and S_f parameters - Exact formula derivation for alpha = 0.1 and epsilon = 3 (appear hand-selected)
- **other_notes:** - Supplement not accessible (referenced at publisher's website but no .txt or .pdf supplement file found in papers folder). Supplementary material reportedly contains clinical assessment details (ADOS-CSS, BRP scale descriptions) but not model details. - The model integrates three components: independent learning (binary correctness), social learning (influence from observing others), and priming (stimulus history effects). The Bayesian integration is implemented as a weighted average rather than formal Bayesian updating. - The paper is published in the Journal of Mathematical Sociology, which may explain the mathematical simulation approach rather than a cognitive modeling approach. - Two phases constitute a single study design (not separate studies), so this is ONE row.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_autism
- pop_children
- pop_healthy_adults
- rr_pop_adolescents
- rr_pop_autism
- rr_pop_children
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- tax_domain_A_influence_transmission
- tax_domain_F_affective_moral
- tax_mod_action_observation
- tax_mod_experiential
- tax_mod_instructed
- tax_model_bayesian
- tax_param_social_weight
- tax_popclass_clinical
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_F_affective_moral
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_decay
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = threat_fear
- tax_rr_topic_social_info_use
- tax_rr_topic_threat_fear
- tax_topic_social_info_use
- tax_topic_threat_fear
