# Khalvati et al. (2016)

- **study_id:** `a7a0c89d37037a4ba_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Khalvati, K., Park, S. A., Dreher, J.-C., & Rao, R. P. N. (2016). A probabilistic model of social decision making based on reward maximization. In *Advances in Neural Information Processing Systems 29 (NIPS 2016)* (pp. 2697-2705). Barcelona, Spain.
- **citation_short:** Khalvati et al. (2016)
- **doi:** Not provided in paper. Conference paper (NIPS 2016).
- **publication_type:** peer-reviewed conference paper
- **year:** 2016.0
- **field_of_study:** Psychology
- **affiliations_raw:** UniversityofWashington InstitutdesSciencesCognitivesMarcJeannerod; LABEX ANR-11-LABEX-0042, ANR-11-IDEX-0007, NSF-ANR ’So-; ethevolunteer’sdilemmaandconductedanexperimentwhere; ethisproblembycombiningaprobabilisticmodelwith; schoolboardsortowncouncils,anddonatingblood; DepartmentofComputerScience CNRSUMR5229; CNRSUMR5229 DepartmentofComputerScience; etheirdecisions,thefeedbackscreenis; emails: dreher@isc.cnrs.fr, park@isc.cnrs.fr, koosha@cs.washington.edu
- **code_url:** 

## Computational level
- **study_focus:** Cooperation learning / social decision making in volunteer's dilemma (Public Goods Game). Bayesian inference of group cooperativeness to maximize expected reward.
- **study_focus_short:** Cooperation learning / social decision making in volunteer's dilemma
- **learning_mode_description:** - Learning mode: Learning from group members' aggregate contribution decisions about group cooperativeness to maximize own expected reward in a Public Goods Game.   - Learning from:     - Source type (social): group (4 other players, actually computer-simulated)     - Source content (social): action/policy (aggregate number of contributors per round)   - Learning about:     - Target type (social): group (cooperativeness of the group)     - Target content (social): state (mental state; cooperativeness parameter $\theta_c$)
- **task_description:** Participants played a Public Goods Game in groups of 5 (actually computer-simulated partners) for 15 rounds per game across 12 feedback games. Each round, they chose to contribute (cost 1 MU) or free-ride; public good (2 MU) was produced if at least k members contributed (k=2 or k=4). Feedback showed total number of other contributors but not individual identities.
- **task_paradigm:** Public goods game
- **players:** Single agent (participant), multi-target (4 simulated group members)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract Public Goods Game screen, binary decision (contribute/free-ride), monetary feedback
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - POMDP model predicts behavior with average round-by-round error of 3.38/15 for k=2 and 2.15/15 for k=4 - POMDP outperforms "Previous Action" descriptive model (fitting error 3.90 for k=2, 3.25 for k=4 over 14 rounds) and "All Actions" descriptive model - LOOCV: POMDP better for k=4 (2.67 vs 3.48); comparable for k=2 (4.23 vs 4.00 but POMDP covers 15 rounds vs 14) - Expected reward predicted by POMDP correlated with bilateral dlPFC activation (right dlPFC peak T = 3.45; left dlPFC T = 3.17) and left ventral striatum (T = 2.98), p < 0.05 FWE corrected within ROI
- **effect_size:** - Right dlPFC: T = 3.45 at (42, 47, 19) - Left dlPFC: T = 3.17 at (-30, 50, 25) - Left ventral striatum: T = 2.98 at (-24, 17, -2) - No Cohen's d, r, or other standardized effect sizes reported (only T-statistics and fitting errors)
- **learning_from:** Group; aggregate contribution decisions of other group members (number of contributors per round)
- **learning_about:** Group; cooperativeness of group ($\theta_c$ parameter)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** POMDP with Beta-Binomial belief updating ($\alpha_0$, $\beta_0$ as initial belief parameters; belief state = Beta($\alpha$, $\beta$) over group cooperativeness $\theta_c$)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** - {"name": "POMDP", "family": "POMDP/Bayesian", "n_params": 2, "metric": "round-by-round error + LOOCV"} - {"name": "Previous Action", "family": "descriptive/Markov", "n_params": 2, "metric": "round-by-round error + LOOCV"} - {"name": "All Actions", "family": "descriptive", "n_params": "not specified (conditional probability table)", "metric": "round-by-round error + LOOCV"}
- **model_mb_mf:** MB (model-based; POMDP is explicitly a forward-planning model with internal model of environment)
- **model_params:** - $\alpha_0$ [S]: initial belief parameter for cooperativeness (contribution count); fitted per subject per k; range 1-100 integers - $\beta_0$ [S]: initial belief parameter for free-riding count; fitted per subject per k; range 1-100 integers - Ratio $\alpha_0$/$\beta_0$: captures prior belief about group cooperativeness - Sum $\alpha_0$ + $\beta_0$: captures weight of prior vs. observations - Mean fitted values: For k=2, $\alpha_0$ > $\beta_0$ on average (higher cooperativeness belief); for k=4, $\alpha_0$ $\approx$ $\beta_0$ (cautious). Exact mean values not reported numerically.
- **social_param:** $\alpha_0$ and $\beta_0$ [S] -- initial belief about group cooperativeness ($\theta_c$); their ratio captures perceived cooperativeness of the social group.
- **social_param_name:** $\alpha_0$
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 1–100
- **model_comparison_metric:** Round-by-round error (average number of incorrectly predicted rounds); Leave-One-Out Cross Validation (LOOCV) error
- **how_model_fit:** individual-level-fit (grid search over $\alpha_0$, $\beta_0$ pairs from 1-100 for each subject and each k)
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) -- GLM with POMDP-derived expected reward as parametric modulator at decision onset
- **contrast:** - Parametric modulation of decision-phase BOLD by POMDP-predicted expected reward for next round, time-locked to outcome onset (duration 4s) - p < 0.05 FWE corrected within a priori ROIs (10mm sphere on dlPFC and ventral striatum)
- **key_regions:** Expected reward signal in bilateral dlPFC and left ventral striatum, FWE-corrected within a priori ROIs.
- **key_regions_abbrev:** VS, striatum, dlPFC
- **coordinates_peak:** - Right dlPFC: 42, 47, 19 - Left dlPFC: -30, 50, 25 - Left ventral striatum: -24, 17, -2
- **analysis_type:** ROI (small volume correction on a priori 10mm spherical ROIs centered on dlPFC and ventral striatum)  ---  ## QUALITY
- **analysis_type_clean:** ROI
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N=29 (30 recruited, 1 excluded due to anxiety; 14 women; mean age 22.97 years, SD 1.99)
- **population_category:** healthy adults
- **population_age_range:** M=22.97
- **ecological_validity:** Low-moderate. Participants believed they played with real humans but actually interacted with a computer algorithm fitted to real PGG behavior from a prior study. Abstract monetary game with no real social interaction. Binary decision space limits ecological validity.
- **eligibility_flag:** Borderline -- the paper frames this as social decision making with Bayesian belief updating over rounds, but the "learning" is belief updating about group cooperativeness across rounds of a repeated game. This is closer to learning over time (belief updating trial-by-trial) than one-shot inference, so it meets inclusion criteria. However, the POMDP is a planning/decision model rather than a pure learning model -- the learning component is the Bayesian belief update embedded within the POMDP framework. Flag: "Borderline learning-vs-decision-making; belief updating over trials qualifies but primary framing is decision-making/planning.
- **concerns:** - Participants played with computer algorithms, not real humans (though algorithm was fitted to real human PGG behavior) - No standardized effect sizes reported (only T-statistics at peak voxels) - Model comparison is based on raw prediction error, not formal statistical model comparison (no BIC/AIC/BMS) - ROI analysis only; no whole-brain results reported - Conference paper (8 pages) -- limited detail on methods - Exact mean fitted parameter values ($\alpha_0$, $\beta_0$) not reported numerically, only described qualitatively and via heatmaps - Model fitting is grid search (brute force) over integer pairs, not MLE or Bayesian estimation in the standard sense
- **limitations_reported:** Authors acknowledge: model ignores empathy among group members (assumes pure self-reward maximization); neural implementation of the model in the brain has not been demonstrated; testing different reward functions (e.g., other-regarding preferences) is left for future work.
- **limitations_categorized:** limited ecological validity; no neural implementation demonstrated; simplified reward function; conference paper length limits methodological detail
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** No
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - effect_size: MEDIUM -- only T-statistics reported, no standardized behavioral effect sizes - model_params (mean fitted values): LOW -- described qualitatively (heatmaps in Fig 3) but exact numerical means not reported - DOI: LOW -- not provided in paper (NIPS 2016 conference proceedings) - eligibility_flag: MEDIUM -- borderline learning vs. decision-making
- **cannot_find:** - DOI (conference paper, not provided) - Exact mean fitted parameter values for $\alpha_0$, $\beta_0$ - Standardized effect sizes (Cohen's d, r, etc.) - Data/code availability
- **other_notes:** This is a NIPS 2016 conference paper (8 pages + references), not a full journal article. The POMDP framework is normative/model-based -- the agent maintains a Bayesian belief (Beta distribution) over group cooperativeness and uses value iteration to compute optimal policy. The "social agent" is a computer algorithm calibrated to real human PGG behavior. The paper sits at the intersection of computational modeling and social neuroscience but is primarily a computational/AI contribution validated with neural data.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_neural = shared
- spec_source = social
- spec_target = social
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MB
- tax_model_bayesian
- tax_param_PE_signal
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = cooperation
- tax_rr_topic_cooperation
- tax_topic_cooperation
