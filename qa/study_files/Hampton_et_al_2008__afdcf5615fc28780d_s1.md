# Hampton et al. (2008)

- **study_id:** `afdcf5615fc28780d_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Hampton, A. N., Bossaerts, P., & O'Doherty, J. P. (2008). Neural correlates of mentalizing-related computations during strategic interactions in humans. *Proceedings of the National Academy of Sciences, 105*(18), 6741-6746. doi:10.1073/pnas.0711099105
- **citation_short:** Hampton et al. (2008)
- **doi:** 10.1073/pnas.0711099105
- **publication_type:** peer-reviewed journal
- **year:** 2008.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** mith,ColumbiaUniversity,NewYork,NY,andapprovedFebruary20,2008(receivedforreviewNovember22,2007); DivisionofHumanitiesandSocialSciences,CaliforniaInstituteofTechnology,1200EastCalifornia; etheactionthatintherecentpastgavethemost; etherdifferent
- **code_url:** 

## Computational level
- **study_focus:** Mentalizing learning; learning about opponent's strategy and how one's own actions influence the opponent's future behavior during competitive strategic interactions.
- **study_focus_short:** Mentalizing learning
- **learning_mode_description:** - Learning mode: Learning from the opponent's actions and the influence of one's own actions on the opponent's strategy, to predict the opponent's future behavior and maximize reward in a competitive game.   - Learning from:     - Source type (social): other (opponent)       - Source content (social): action/policy (opponent's observed actions and their responsiveness to one's own actions)   - Learning about:     - Target type (social): other (opponent)       - Target content (social): state (mental state; opponent's strategy/intentions and how they are influenced by one's own actions)
- **task_description:** Two participants play a competitive "inspection game" (generalized matching pennies) in which one player is the "employer" who can inspect or not inspect, and the other is the "employee" who can work or shirk. Payoffs are asymmetric and competitive: when one player wins, the other loses. Players alternate roles across sessions of 100 trials each.
- **task_paradigm:** Matching pennies
- **players:** Multi-agent (dyad), asymmetric (employer vs. employee roles, alternating across sessions)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Abstract binary choice options (inspect/not inspect; work/shirk), monetary outcomes (0-100 cents per trial)
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - Influence model fit behavior significantly better than RL or fictitious play models (P < 0.005, paired t-test; out-of-sample log-likelihood: Influence = 0.674 +/- 0.004, Fictitious = 0.685 +/- 0.003, RL = 0.687 +/- 0.003 -- lower is better)   - Expected reward signal from influence model correlated with mPFC activity significantly better than RL model (P < 0.005, ROI paired t-test)   - Influence update signal correlated with bilateral pSTS activity (P < 0.05 SVC)   - Prediction error signals correlated with bilateral ventral striatum (z = 4.97 and z = 4.73, P < 0.05 whole-brain corrected)   - Between-subject correlation: degree of influence-based strategizing covaried with influence signal in dmPFC (z = 4.09, P < 0.05 SVC)   - Interregion correlations: mPFC activity at outcome better predicted by linear combination of STS + ventral striatum than either alone (P < 10^-6)   - Switch vs. nonswitch BOLD difference in mPFC for employee > employer (P = 0.02)
- **effect_size:** - Main Results:   - Influence model fit behavior significantly better than RL or fictitious play models (P < 0.005, paired t-test; out-of-sample log-likelihood: Influence = 0.674 +/- 0.004, Fictitious = 0.685 +/- 0.003, RL = 0.687 +/- 0.003 -- lower is better)   - Expected reward signal from influence model correlated with mPFC activity significantly better than RL model (P < 0.005, ROI paired t-test)   - Influence update signal correlated with bilateral pSTS activity (P < 0.05 SVC)   - Prediction error signals correlated with bilateral ventral striatum (z = 4.97 and z = 4.73, P < 0.05 whole-brain corrected)   - Between-subject correlation: degree of influence-based strategizing covaried with influence signal in dmPFC (z = 4.09, P < 0.05 SVC)   - Interregion correlations: mPFC activity at outcome better predicted by linear combination of STS + ventral striatum than either alone (P < 10^-6)   - Switch vs. nonswitch BOLD difference in mPFC for employee > employer (P = 0.02)
- **learning_from:** Other (opponent); opponent's actions and the influence one's own actions have on the opponent's strategy.
- **learning_about:** Other (opponent); opponent's strategy/mental state -- specifically, how the opponent adapts behavior in response to one's own actions.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Influence learning model: p*_{t+1} = p*_t + alpha_1 (P_t - p*_t) + alpha_2 * 4*beta*p*_t(1-p*_t)(Q_t - q**_t). Extends fictitious play with an influence update term tracking how one's own actions change the opponent's strategy. Parameters: alpha_1 (learning rate for opponent's actions), alpha_2 (weighting of influence update), beta (inverse temperature).
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning / Belief updating
- **all_models_tested:** - {"name": "Reinforcement Learning (RL)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "log-likelihood (out-of-sample)"} - {"name": "Fictitious Play", "family": "Fictitious play (belief-based)", "n_params": 2, "metric": "log-likelihood (out-of-sample)"} - {"name": "RL + Fictitious (EWA)", "family": "Experience-weighted attraction", "n_params": 3, "metric": "log-likelihood (out-of-sample)"} - {"name": "Influence Model", "family": "Fictitious play with influence extension", "n_params": 3, "metric": "log-likelihood (out-of-sample)"}
- **model_mb_mf:** MB (model-based; the influence model requires a model of the opponent's strategy and how it responds to one's own actions)
- **model_params:** - alpha (learning rate for updating opponent's strategy estimate): Employer = 0.21, Employee = 0.038 [S] - beta (inverse temperature / exploration-exploitation): Employer = 0.090, Employee = 0.059 - omega (influence weight parameter, alpha_2 in the influence term): Employer = 0.0011, Employee = 0.043 [S]  Note: The supplement Table S1 labels the parameters as beta (exploration), alpha (learning rate), and omega (influence weight). All parameters are social in nature as they govern learning about a social opponent, but omega is the key social parameter as it specifically captures influence on the opponent.
- **social_param:** omega (influence weight) -- captures the degree to which a player's own actions influence the opponent's strategy update. This is the uniquely social parameter that distinguishes the influence model from standard fictitious play.
- **social_param_name:** alpha
- **social_param_value:** 0.21
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Log-likelihood (out-of-sample cross-validation: trained on first 70 trials, tested on last 30)
- **how_model_fit:** individual-level-fit (parameters fitted by maximizing logistic log-likelihood across all subjects simultaneously, with separate parameters for employer and employee roles)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) -- expected value from influence model used as parametric modulator at choice onset; prediction error and influence update signals used as parametric modulators at outcome.
- **contrast:** - Expected reward (influence model) at time of choice: mOFC (0, 36, -21; z = 3.56), mPFC (-3, 63, 15; z = 3.29, P < 0.05 SVC), right temporal pole (42, 15, -39; z = 3.98) - Influence model > RL model expected reward: mid-to-dorsal mPFC (-3, 57, 12; z = 3.11, P < 0.05 SVC) - Influence update signal at outcome: bilateral STS (-57, -54, 0; z = 3.32 and 60, -54, 9; z = 3.35, both P < 0.05 SVC) - Between-subject influence covariation: dmPFC (-3, 51, 24; z = 4.09, P < 0.05 SVC) - Prediction error at outcome: bilateral ventral striatum (9, 6, -18; z = 4.97 and -9, 9, -18; z = 4.73, both P < 0.05 whole-brain corrected), mPFC (-9, 57, 6; z = 4.35), paracingulate cortex (12, 36, 18; z = 4.62)
- **key_regions:** Expected reward signal from influence model in mPFC and mOFC; influence update signal in bilateral pSTS; prediction error in bilateral ventral striatum and mPFC; between-subject influence strategizing differences in dmPFC. Interregion correlation analysis showed mPFC activity at outcome predicted by linear combination of STS and ventral striatum signals.
- **key_regions_abbrev:** VS, striatum, mPFC, dmPFC, OFC, STS
- **coordinates_peak:** mOFC (expected value, influence model): 0, 36, -21 mPFC (expected value, influence model): -3, 63, 15 Right temporal pole (expected value): 42, 15, -39 mPFC (influence > RL expected value): -3, 57, 12 Left STS (influence update): -57, -54, 0 Right STS (influence update): 60, -54, 9 dmPFC (between-subject influence covariation): -3, 51, 24 Right ventral striatum (prediction error): 9, 6, -18 Left ventral striatum (prediction error): -9, 9, -18 mPFC (prediction error): -9, 57, 6 Paracingulate cortex (prediction error): 12, 36, 18
- **analysis_type:** both (whole-brain voxel-wise comparisons with small-volume correction for mentalizing network regions derived from Frith & Frith 2003 meta-analysis; plus ROI analysis in 8-mm sphere in mPFC)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 32 total (16 scanned, 16 played outside scanner in pairs); one pair excluded for collusion, leaving N = 30 for behavioral analyses and N = 15 for fMRI. Age: 25 +/- 1 years; 7 female among scanned subjects.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Competitive game played against a real human opponent (not a computer), increasing ecological validity for social interaction. However, the inspection game is an abstract, simplified competitive scenario with only two choices per trial, limiting generalizability to real-world social interactions. Participants were strangers, and communication was not possible.
- **eligibility_flag:** 
- **concerns:** Relatively small fMRI sample (n = 15); parameters were fitted to all subjects simultaneously rather than individually, which may obscure individual differences; small-volume correction based on prior meta-analysis coordinates rather than independent functional localizer; the inspection game is zero-sum with only two actions, limiting complexity of strategic reasoning studied; no parameter recovery or model recovery analyses reported.
- **limitations_reported:** Authors acknowledge: humans always faced real human opponents, leaving open whether similar mechanisms engage when playing adaptive non-human computers; unclear whether other animals besides humans have the capacity for sophisticated strategic computations of this sort; the study addresses how players understand the effects of influencing the opponent but not how they could use that knowledge to alter the opponent's behavior to receive bigger future rewards (e.g., reputation building, teaching, or Stackelberg strategies).
- **limitations_categorized:** limited ecological validity; task simplicity; limited generalizability; no parameter recovery; no model recovery; small sample size
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
- **wc_rule10:** Partial
- **wc_score:** 6.0
- **wc_total:** 6.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM confidence -- parameters reported in supplement Table S1, but the paper fits parameters simultaneously across all subjects rather than reporting individual-level distributions. The labels (alpha, beta, omega) are inferred from context matching the supplement table ordering to the model equations. - effect_size: MEDIUM confidence -- effect sizes are reported as z-scores and p-values from SPM analyses; no standard effect size measures (Cohen's d, r, etc.) for behavioral model comparisons. - wc_guidelines rule 8: MEDIUM confidence -- scored as Partial based on Fig. 1D showing model-predicted vs. actual choice probabilities, which serves as an informal validation but is not a formal posterior predictive check.
- **cannot_find:** Standard behavioral effect sizes (Cohen's d, r) for model comparison; individual-level parameter distributions; formal model validation statistics; data/code availability statement.
- **other_notes:** This is an early and influential paper in computational mentalizing. The "influence model" is a key contribution -- it extends fictitious play by adding a second-order belief term that captures how one's own actions influence the opponent's strategy. The paper demonstrates a dissociation in the mentalizing network: mPFC tracks expected value incorporating influence, pSTS tracks influence update signals, and ventral striatum tracks standard prediction errors. The interregion correlation analysis (Fig. 4) provides early evidence for a functionally interacting mentalizing network. Published in PNAS, 2008.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = structural
- spec_locus = source+target
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_mod_active_interaction
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MB
- tax_model_bayesian
- tax_param_PE_signal
- tax_param_learning_rate
- tax_param_social_weight
- tax_param_temperature
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = strategic_reasoning
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_mentalizing
- tax_rr_topic_strategic_reasoning
- tax_topic_mentalizing
- tax_topic_strategic_reasoning
