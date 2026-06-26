# Witt et al. (2023)

- **study_id:** `ac9c48d17a2ad451e_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Witt, A., Toyokawa, W., Lala, K., Gaissmaier, W., & Wu, C. M. (2023). Social learning with a grain of salt. In M. Goldwater, F. K. Anggoro, B. K. Hayes, & D. C. Ong (Eds.), *Proceedings of the 45th Annual Conference of the Cognitive Science Society*. [CC BY 4.0]
- **citation_short:** Witt et al. (2023)
- **doi:** Not reported in the text.
- **publication_type:** conference proceedings (peer-reviewed)
- **year:** 2023.0
- **field_of_study:** Psychology
- **affiliations_raw:** mitedto pleflexiblyintegratesocialinformationwithindividuallearn-; Lab,UniversityofTu¨bingen,Tu¨bingen,Germany; UniversityofKonstanz,Konstanz,Germany; UniversityofStAndrews,StAndrews,UK; ethesociallycor- strator(Najaretal; ethanassumedbymodelsfrom; ethemostrewardingtoyou; mitation(Toyokawaetal; emails: alexandra.witt@gmx.net
- **code_url:** 

## Computational level
- **study_focus:** Social generalization learning — how humans integrate social information from others with different reward functions into their own learning via generalization, treating social information as noisier than individual information.
- **study_focus_short:** Social generalization learning
- **learning_mode_description:** - Learning mode: Learning from others' choices and outcomes about the value of options in a spatially correlated reward environment, where others have correlated but non-identical reward functions.   - Learning from:     - Source type (social): other (group members, 3 others in group of 4)     - Source content (social): outcomes (reward outcomes of others' choices)   - Learning about:     - Target type (non-social): world (reward environment — spatial distribution of rewards)     - Target content (non-social): state (expected reward values across spatial grid)
- **task_description:** Participants searched for rewards on a spatial grid (socially correlated bandit) in groups of four, where each participant had personalized but correlated reward environments. Over 14 trials per round (8 rounds), participants chose grid tiles to maximize reward, while observing all other group members' choices and outcomes after each trial.
- **task_paradigm:** Social bandit / herding
- **players:** Multi-agent (group of 4 participants), symmetric.
- **n_players:** small group (3-4)
- **partner_type:** human (live)
- **stimuli:** Spatial grid (alien ocean cover story), numerical reward outcomes, color-coded reward displays for self and 3 others.
- **method:** online / behavioural
- **method_full:** Behavioural (online experiment via Prolific)
- **main_result:** - Social Generalization (SG) was the dominant model in evolutionary simulations (p(SG) = .998 at final generation) - Bayesian model selection: SG was best model (pxp(SG) = .63; R² = 0.29 ± 0.09 SD) - Asocial Learning also somewhat prevalent (pxp(AS) = .23) - Decision Biasing and Value Shaping were not common - Participants with lower social noise parameter (more social information use) achieved higher rewards (r_τ = −.28, BF > 100) - Length-scale estimates significantly lower than ground truth (d = 1.7, BF > 100) - Model recovery: all p(gen|fit) ≥ .83, p(fit|gen) ≥ .80, r_τ ≥ .75 - Interaction effect between information source and previous reward on search distance (β = 1.23, HDI [1.18, 1.28])
- **effect_size:** - Cohen's d = 1.7 (λ estimate vs. ground truth) - r_τ = −.28 (social noise parameter vs. mean reward) - BF > 100 (multiple comparisons) - R² = 0.29 ± 0.09 (SG model fit)
- **learning_from:** Other (3 group members); choices and reward outcomes on spatial grid.
- **learning_about:** World; expected reward values across options in a spatially correlated environment.  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Social Generalization (GP-UCB with social noise parameter: λ, β, τ, ε_soc)  Formula: GP regression with σ² = ε_ind + δ_soc × ε_soc (Eq. 7), where social observations receive higher assumed noise; UCB value function V(x) = m(x) + β√v(x); softmax policy π(x) ∝ exp(V(x)/τ)
- **model_family:** Gaussian process
- **model_class:** Other
- **all_models_tested:** - {"name": "Asocial Learning (AS)", "family": "Gaussian Process (GP-UCB)", "n_params": 3, "metric": "pxp (hierarchical BMS)"} - {"name": "Decision Biasing (DB)", "family": "GP-UCB + frequency-based social copying", "n_params": 4, "metric": "pxp (hierarchical BMS)"} - {"name": "Value Shaping (VS)", "family": "GP-UCB + social prediction error value update", "n_params": 4, "metric": "pxp (hierarchical BMS)"} - {"name": "Social Generalization (SG)", "family": "GP-UCB + social noise parameter", "n_params": 4, "metric": "pxp (hierarchical BMS)"}
- **model_mb_mf:** MB (model-based — uses an internal generative model via Gaussian Process to predict reward structure)
- **model_params:** - λ (length-scale): controls spatial generalization breadth; mean fitted = 1.11 - β (exploration bonus): trades off exploitation vs. exploration; mean fitted = 0.29 - τ (softmax temperature): choice stochasticity; mean fitted = 0.06 - ε_soc [S] (social noise): additional noise assumed for social observations; median fitted = 26.4
- **social_param:** ε_soc — social noise parameter controlling the assumed noisiness of social information relative to individual observations. Higher values mean less reliance on social information. Evolved optimal value = 3.29; human median = 26.4 (indicating underreliance on social information).
- **social_param_name:** ε_soc
- **social_param_value:** 26.4
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Protected exceedance probability (pxp) via hierarchical Bayesian model selection (Rigoux et al., 2014); leave-one-out cross-validation.
- **how_model_fit:** Individual-level fit (leave-one-out cross-validation, individual parameter estimates shown)
- **data_type_fit_to:** Choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 188 recruited; N = 128 after excluding groups with drop-out (mean age: 38.5 ± 12.7 SD; 44 females). Online experiment via Prolific.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** The socially correlated bandit improves on previous paradigms by introducing personalized but correlated rewards, mimicking real-world settings where social information must be adjusted for individual differences (e.g., restaurant reviews, matters of taste). However, the task is still a lab-based grid search with abstract rewards and time pressure (10s choice deadline), limiting naturalistic social interaction. Groups were yoked (not face-to-face) and communication was limited to observing choices/outcomes.
- **eligibility_flag:** 
- **concerns:** Conference proceedings paper (6 pages) — relatively brief methods and results. No supplement available. The paper reports evolutionary simulations and behavioral model fitting but does not report neural data. The 10-second time limit on choices led to 0.78% random choice trials excluded — minimal but worth noting. The paper acknowledges participants substantially underutilized social information relative to what evolutionary simulations suggest is optimal.
- **limitations_reported:** GP-UCB parameter estimates differ from prior literature, possibly because social learning replaced some individual exploration; median social noise parameter far higher than evolved optimal, suggesting underreliance on social information; no control over quality of social information available to participants in real groups; task only examines positively correlated social information; no claims made about how value of others' options is inferred from actions; shorter search horizons could incentivize more social learning but may push model estimation limits; some participants may have found the interface too overwhelming to consider multiple information sources.
- **limitations_categorized:** Parameter estimation differences from prior work; underreliance on social information; limited experimental control over social information quality; limited ecological validity (positive correlations only); no inference mechanism modeled; task design constraints; participant cognitive load.
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 9.0
- **wc_total:** 9.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - doi: MEDIUM — not reported in extracted text; conference proceedings may have DOI but it was not included - citation author name: MEDIUM — the text shows "KevinLala" with footnote "§formerlyLaland" suggesting this is Kevin Laland (name change); cited as "Lala" per the paper - wc_8 (model validation): MEDIUM — qualitative comparison shown but no formal posterior predictive check - wc_10 (transparency): MEDIUM — no explicit data/code sharing statement found
- **cannot_find:** - DOI - Supplement (none exists for this conference paper) - Exact BIC/AIC values (only pxp reported) - Pre-registration status
- **other_notes:** This is a conference proceedings paper from CogSci 2023, not a full journal article — hence brevity in some sections. The author listed as "Kevin Lala" with note "§formerly Laland" is Kevin Laland (University of St Andrews), a prominent cultural evolution researcher. The Social Generalization model is novel to this paper. The evolutionary simulation approach to normative model evaluation is methodologically notable. The paper finds humans can integrate social information flexibly even when it cannot be used verbatim, but substantially underweight it relative to the normative optimum.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_multiplayer_live
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = parametric
- spec_locus = source+context
- spec_source = social
- tax_domain_A_influence_transmission
- tax_mod_experiential
- tax_mod_multiplayer_live
- tax_mod_vicarious_outcome
- tax_model_MB
- tax_model_gaussian_process
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = gaussian_process
- tax_rr_model_gaussian_process
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_topic_social_info_use
- tax_topic_social_info_use
