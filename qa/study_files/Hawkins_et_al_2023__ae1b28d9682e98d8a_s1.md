# Hawkins et al. (2023)

- **study_id:** `ae1b28d9682e98d8a_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Hawkins, R. D., Berdahl, A. M., Pentland, A., Tenenbaum, J. B., Goodman, N. D., & Krafft, P. M. (2023). Flexible social inference facilitates targeted social learning when rewards are not observable. *Nature Human Behaviour*, *7*(10), 1767–1776. https://doi.org/10.1038/s41562-023-01682-x
- **citation_short:** Hawkins et al. (2023)
- **doi:** 10.1038/s41562-023-01682-x
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Psychology
- **affiliations_raw:** mitation, rather than relying on their own independent (asocial) in social-learning experiments often use hybrid strategies, combin-; mitation must view social-learning behaviour not as the application of an inventory; School of Aquatic and Fishery Sciences, University of Washington, Seattle, WA, USA; mpirical and computational work in cognitive science and their own outcomes; Department of Psychology, University of Wisconsin–Madison, Madison, WI, USA; mita- ing multiple sources of ‘who’ and ‘when’ information, or deploy dif-; Department of Computer Science, Stanford University, Stanford, CA,
- **code_url:** https://github.com/hawkrobe/

## Computational level
- **study_focus:** Social learning via social inference — how individuals infer others' hidden success from observable behavioural trajectories to guide targeted social learning in a collective-sensing task.
- **study_focus_short:** Social learning via social inference
- **learning_mode_description:** - Learning mode: Inferring others' hidden reward states from observable movement trajectories to guide selective copying in a collective-sensing task.   - Learning from:     - Source type (social): other (group members / artificial agents)     - Source content (social): action/policy (movement trajectories — stopping, slowing, spinning behaviour)   - Learning about:     - Target type (non-social): world (spatial location of hidden reward region)     - Target content (non-social): state (world state; location of high-scoring region)
- **task_description:** Participants controlled avatars in a virtual environment where a hidden, slowly drifting circular scoring region determined rewards at each spatial location. Participants could observe others' movement trajectories but not their scores, and had to balance independent exploration with selective social learning to maximize cumulative reward.
- **task_paradigm:** Social network learning
- **players:** Multi-agent (groups of 1–6 human participants in Exp 1 & 3; single agent with 4 artificial bots in Exp 2), symmetric (Exp 1 & 3) / asymmetric with bots (Exp 2).
- **n_players:** 
- **partner_type:** computer (algorithmic)
- **stimuli:** Virtual spatial environment (480 × 285 pixels), avatar triangles, hidden binary or gradient score field, movement trajectory cues (stopping/slowing/spinning).
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - Exp 1: Larger groups achieved significantly higher scores in second half (b = 0.87, 95% CI [0.26, 1.44], t(6.6) = 2.9)   - Exp 1: Participants moved ~half as fast when reward present vs absent (d̂ = 2.5, 95% CI [2.37, 2.62])   - Exp 2: Selective copying of exploiting agents only when not receiving reward (interaction: b = 47.6, 95% CI [7.5, 85.4], t(25.5) = 2.5)   - Exp 3: Scores increased with group size (b = 0.53, 95% CI [0.17, 0.88], t(81.6) = 2.9)   - Exp 3: Scores higher in low-noise than high-noise condition (b = −0.04, 95% CI [−0.06, −0.01], t(9.2) = 3.6)   - Exp 3: Group size × noise interaction (b = 0.43, 95% CI [−0.78, −0.07], t(81.6) = 2.3)   - Exp 3: Strong effect of current score on exploit probability (b = 3.22, 95% CI [3.19, 3.24], z = 311)   - Exp 3: Score × noise interaction on exploit behaviour (b = −0.35, 95% CI [−0.37, −0.33], z = −33.9)   - Only the social inference model (not heuristic models) could account for the magnitude of empirical group size effects
- **effect_size:** - Main Results:   - Exp 1: Larger groups achieved significantly higher scores in second half (b = 0.87, 95% CI [0.26, 1.44], t(6.6) = 2.9)   - Exp 1: Participants moved ~half as fast when reward present vs absent (d̂ = 2.5, 95% CI [2.37, 2.62])   - Exp 2: Selective copying of exploiting agents only when not receiving reward (interaction: b = 47.6, 95% CI [7.5, 85.4], t(25.5) = 2.5)   - Exp 3: Scores increased with group size (b = 0.53, 95% CI [0.17, 0.88], t(81.6) = 2.9)   - Exp 3: Scores higher in low-noise than high-noise condition (b = −0.04, 95% CI [−0.06, −0.01], t(9.2) = 3.6)   - Exp 3: Group size × noise interaction (b = 0.43, 95% CI [−0.78, −0.07], t(81.6) = 2.3)   - Exp 3: Strong effect of current score on exploit probability (b = 3.22, 95% CI [3.19, 3.24], z = 311)   - Exp 3: Score × noise interaction on exploit behaviour (b = −0.35, 95% CI [−0.37, −0.33], z = −33.9)   - Only the social inference model (not heuristic models) could account for the magnitude of empirical group size effects
- **learning_from:** other (group members); observable movement trajectories (stopping/slowing/spinning as cues to hidden reward)
- **learning_about:** world; spatial location of hidden high-scoring region  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** Bayesian social inference model: P(r_i^t | τ_i^{0:t}) ∝ P(τ_i^t | r_i^t) P(r_i^t) — agent infers others' hidden reward from behavioural trajectory using Bayes' rule; 1 free parameter (ε, noise/error in exploiting behaviour)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** [   {"name": "Social inference model", "family": "Bayesian belief updating", "n_params": 1, "metric": "qualitative simulation comparison"},   {"name": "Asocial model", "family": "random exploration", "n_params": 1, "metric": "qualitative simulation comparison"},   {"name": "Move-to-centre heuristic", "family": "heuristic", "n_params": 1, "metric": "qualitative simulation comparison"},   {"name": "Naive-copy heuristic", "family": "heuristic", "n_params": 1, "metric": "qualitative simulation comparison"} ]
- **model_mb_mf:** Bayesian
- **model_params:** - ε (epsilon): noise parameter reflecting probability of failing to exploit when receiving reward. Best quantitative fit at ε = 0.15. [S] — governs social inference reliability. - θ_exp (independent explore probability): free parameter for heuristic models governing frequency of independent exploration vs social heuristic. Best-fitting: θ̂_exp = 0.3 (move-to-centre), θ̂_exp = 0.1 (naive-copy).
- **social_param:** ε (epsilon) — noise parameter reflecting how reliably agents' exploiting behaviour signals underlying reward, which determines the quality of social inference about others' hidden success.
- **social_param_name:** ε
- **social_param_value:** 0.15
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Qualitative comparison of simulated group performance curves against empirical data (no formal BIC/AIC — models compared by whether simulated performance at best-fitting parameter values could account for magnitude of empirical group size effect).
- **how_model_fit:** simulate-and-compare
- **data_type_fit_to:** choice behavior (movement trajectories, group-level average scores)  ---  ### IMPLEMENTATION LEVEL

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
- **sample_size:** Exp 1: N = 682 (294 groups, sizes 1–6); Exp 2: N = 28 (single-participant sessions with bots); Exp 3: N = 454 (224 groups, sizes 1–5; 116 low-noise, 338 high-noise). Total N = 1,164. All recruited from Amazon Mechanical Turk, United States.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Real-time interactive web-based experiment with multiple human participants, which is more ecologically valid than typical solo lab tasks. However, the virtual environment is still highly simplified relative to real-world social learning contexts (abstract spatial navigation rather than naturalistic social interaction). The task draws on collective-sensing paradigms originally designed for fish schools.
- **eligibility_flag:** 
- **concerns:** Model comparison is purely qualitative (simulation-based comparison of group-level performance curves rather than formal statistical model comparison at the individual level). No parameter recovery, no formal model fitting to individual behaviour (only ε = 0.15 noted as giving reasonable quantitative fit). The social inference model is compared at the group level, not fitted to individual choice data. The models have minimal parametric structure (1 free parameter each), which limits the depth of computational characterisation.
- **limitations_reported:** Our initial power analysis did not take into account the stronger three-way interaction needed to test the difference between these interactions; hence, better estimating the baseline variability of clicks in non-social environments is likely to be a fruitful target for future work using a more highly powered sample"; "Extending our model to a more granular level of analysis, including human attention patterns, is an exciting direction for future work"; the interaction between noise condition and group size in Exp 3 was weak and authors caution about over-interpreting it given imbalances in sample sizes across noise conditions.
- **limitations_categorized:** limited statistical power; task simplicity; limited model granularity; sample size imbalance across conditions
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Partial
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Partial
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_comparison_metric: MEDIUM confidence — no formal statistical metric used; comparison is qualitative (simulated vs empirical performance curves) - winning_model parameters: MEDIUM confidence — ε = 0.15 mentioned as giving reasonable fit but no formal fitting procedure described - wc_guidelines rule 4 (fit parameters): MEDIUM — parameters identified via grid search over simulations, not formal fitting to individual data - preregistered: LOW — not mentioned anywhere in paper or supplement
- **cannot_find:** - Formal model comparison statistics (BIC, AIC, etc.) — not used in this paper - Individual-level model fitting results - Preregistration status
- **other_notes:** This paper is primarily a computational/behavioural study bridging social cognition and collective behaviour literatures. The Bayesian social inference model is relatively simple (1 parameter) and is compared at the group level via simulation rather than fitted to individual behaviour. The paper spans 3 experiments with increasing complexity. The supplement contains only screenshots and example gameplay reconstructions, no additional modeling details. The paper's core contribution is demonstrating that Bayesian social inference can explain empirical group size effects that simpler heuristic models cannot.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_mentalizing_inference
- rr_tax_mod_multiplayer_live
- spec_context = social
- spec_depth = parametric
- spec_locus = source
- spec_source = social
- tax_domain_A_influence_transmission
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_mod_mentalizing_inference
- tax_mod_multiplayer_live
- tax_model_bayesian
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_mentalizing
- tax_rr_topic_social_info_use
- tax_topic_mentalizing
- tax_topic_social_info_use
