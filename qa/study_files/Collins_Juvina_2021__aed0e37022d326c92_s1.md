# Collins & Juvina (2021)

- **study_id:** `aed0e37022d326c92_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Collins, M. G., & Juvina, I. (2021). Trust miscalibration is sometimes necessary: An empirical study and a computational model. *Frontiers in Psychology*, *12*, 690089. https://doi.org/10.3389/fpsyg.2021.690089
- **citation_short:** Collins & Juvina (2021)
- **doi:** 10.3389/fpsyg.2021.690089
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Psychology
- **affiliations_raw:** College, United States reconstructed their trust-investment portfolios by discounting their trust in their previously; Laboratory, Department of Psychology, Wright State University, Dayton, OH, United States; University of Plymouth, when and with whom to interact among multiple agents; University of Southern California,; section: dynamic environments; mpirical and computational; section of the journal; mpirical Study and a; emails: ion.juvina@wright.edu
- **code_url:** 

## Computational level
- **study_focus:** Trust learning — trust calibration, trust discounting, and trust necessity in multi-agent strategic interaction
- **study_focus_short:** Trust learning
- **learning_mode_description:** - Learning mode: Learning from counterparts' reciprocation behavior (returns) about their trustworthiness, and adjusting trust-investment portfolios across multiple partners   - Learning from:     - Source type (social): other (three confederate agents / counterparts)     - Source content (social): outcomes (points returned by counterparts)   - Learning about:     - Target type (social): other (three confederate agents / counterparts)     - Target content (social): state (mental state; trustworthiness)
- **task_description:** In the multi-arm trust game (MATG), a single participant (Sender) receives a 40-point endowment each round and freely allocates points among three confederate Receivers (who vary in interaction frequency: high, medium, low). Receivers multiply allocated points by 4 and return a proportion; across 120 rounds, confederate trustworthiness shifts from high (75% return) to neutral (25% return) at round 70.
- **task_paradigm:** Trust game
- **players:** Single agent (participant as Sender), multi-target (3 confederate Receiver agents with predetermined behavior)
- **n_players:** multi-target (3+)
- **partner_type:** confederate
- **stimuli:** Color-coded counterparts (labeled "receiver" or "computer"), point allocations, numeric feedback on returns
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Significant three-way interaction between interaction schedule, strategy, and round on allocation, F(2, 10,030) = 308.8, p < 0.001 (Cohen's f = 0.25) - Significant three-way interaction between identity (animacy/inanimacy), strategy, and round, F(1, 10,030) = 8.73, p < 0.001 (Cohen's f = 0.03) - Under high trustworthiness, allocations increased to high-frequency agent but decreased to medium/low-frequency agents (trust discounting) - When trustworthiness shifted to neutral, participants sharply decreased trust in previously trusted (high-frequency) agent and temporarily increased trust in previously distrusted (medium/low-frequency) agents — evidence of trust development strategy driven by trust necessity - Full ACT-R trust model fit to data: r = 0.92, RMSD = 0.14 (full experiment); r = 0.83, RMSD = 1.05 (neutral strategy phase) - State trust survey: main effect of interaction schedule, F(2, 48) = 13.33, p < 0.001 (Cohen's f = 0.75) - Model inferred trust accumulator correlated with participant behavior: r(358) = 0.99; trust-invest accumulator: r(358) = 0.91
- **effect_size:** - Three-way interaction (schedule × strategy × round): Cohen's f = 0.25 - Three-way interaction (identity × strategy × round): Cohen's f = 0.03 - State trust effect of interaction schedule: Cohen's f = 0.75 - Trait trust vs. first-round allocation: r = 0.33 (non-significant) - Full trust model fit (full experiment): r = 0.92, RMSD = 0.14 - Full trust model fit (neutral phase): r = 0.83, RMSD = 1.05 - Model inferred trust accumulator: r = 0.99 - Model inferred trust-invest accumulator: r = 0.91
- **learning_from:** Other (three confederate agents); outcomes (points returned and interaction availability)
- **learning_about:** Other (three confederate agents); trustworthiness / trust-investment portfolio  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** ACT-R cognitive model with instance-based learning (IBL), sequence learning, trust accumulator, and trust-invest accumulator; 5 fitted parameters (trust accumulator threshold, trust-invest accumulator threshold, trust discounting parameter, procedural learning rate, noise parameter)
- **model_family:** Cognitive architecture (ACT-R/IBL)
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Full trust model", "family": "ACT-R (IBL + trust + trust-invest accumulators)", "n_params": 5, "metric": "r, RMSD"},   {"name": "Trust model (no trust-invest accumulator)", "family": "ACT-R (IBL + trust accumulator only)", "n_params": "not specified", "metric": "r, RMSD"},   {"name": "No trust model (no trust or trust-invest accumulators)", "family": "ACT-R (IBL only)", "n_params": "not specified", "metric": "r, RMSD"} ]
- **model_mb_mf:** MB (model-based — the ACT-R model uses instance-based learning to generate predictions about counterpart behavior and makes forward-looking decisions based on trust necessity)
- **model_params:** - Trust accumulator threshold [S]: governs transition between trust and distrust states (mean fitted value not reported) - Trust-invest accumulator threshold [S]: governs transition to trust necessity state, triggering trust development strategy (mean fitted value not reported) - Trust discounting parameter [S]: rate at which prior trust is discounted as a function of recency of interaction (mean fitted value not reported) - Procedural learning rate: ACT-R's reward-based learning rate for procedural memory (mean fitted value not reported) - Noise parameter: stochastic noise in the model (mean fitted value not reported)
- **social_param:** Trust accumulator [S] — indexes state trust in a counterpart; Trust-invest accumulator [S] — indexes trust necessity, triggering trust development strategy when trust is low; Trust discounting parameter [S] — rate at which prior trust decays with infrequent interaction
- **social_param_name:** Trust accumulator threshold
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Correlation (r) and root-mean-squared deviation (RMSD) — compared across full experiment, high trustworthiness phase, and neutral trustworthiness phase
- **how_model_fit:** simulate-and-compare (model simulated to generate allocations, fit evaluated by r and RMSD against average human allocations)
- **data_type_fit_to:** choice behavior (point allocations as behavioral proxy for trust)  ---  ### IMPLEMENTATION LEVEL

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
- **sample_size:** N = 44 recruited (Age: M = 38.25, SD = 11.8; 17% female); after data cleaning, 11 excluded (6 animacy, 5 inanimacy), leaving N = 33 analyzed
- **population_category:** healthy adults
- **population_age_range:** M=38.25 (SD=11.8)
- **ecological_validity:** The MATG improves ecological validity over standard trust game by allowing choice of when and with whom to interact among multiple agents, continuous allocation decisions, and variable interaction schedules. However, counterparts were confederate agents with predetermined behavior (not truly interactive), and the task was conducted online via AMT with monetary incentives. The closed-loop trust development dynamics that the authors argue for could not fully manifest because counterparts did not adapt to participant behavior.
- **eligibility_flag:** FLAG — The "social agents" are confederate automated agents with predetermined behavior, not genuine social partners. The paper studies trust learning, which is social in context, but the counterparts do not adapt. Additionally, the computational model is an ACT-R cognitive architecture model rather than a standard computational model in the RL/Bayesian sense; it is a process model rather than a normative or algorithmic-level model in the typical computational psychiatry sense. The paper meets inclusion criteria (computational modeling, human behavioral data, learning in social context, learning over time) but should be flagged for the nature of the social agent and the model type.
- **concerns:** - Fitted parameter values are not reported — only the number of parameters and general descriptions are provided - The number of free parameters in the lesioned models is not specified - No formal model comparison metric (e.g., AIC, BIC) was used to compare the three ACT-R models — only r and RMSD - 11 of 44 participants (25%) were excluded based on cluster analysis, which is a high exclusion rate - The animacy vs. inanimacy manipulation produced only a very small effect (Cohen's f = 0.03), and the authors themselves note it contradicts prior literature - Counterparts were confederate agents, so the claimed "trust development strategy" could never actually succeed in this paradigm - The ACT-R model extends previous models (Juvina et al., 2015, 2019) but exact equations/formulas are not provided in this paper — readers are referred to prior publications
- **limitations_reported:** The pattern of results may not generalize to different cutoff points for trustworthiness (75%/25%) and interaction frequency (1/3/6 trials); two independent variables were treated as nominal though they could take many values; the trust development strategy could not succeed because confederates maintained neutral strategy regardless of participant behavior
- **limitations_categorized:** limited generalizability; task simplicity; ecological validity (predetermined confederate behavior); parameter reporting transparency
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Partial
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.0
- **wc_total:** 5.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - winning_model: MEDIUM — model formula/equations not provided in this paper; described verbally and by reference to Juvina et al. (2015, 2019) - model_params: LOW — parameter names described but no fitted values reported; number of parameters in lesioned models not specified - model_mb_mf: MEDIUM — classified as MB because the model makes forward predictions using IBL, but this is an ACT-R architecture model, not a standard MB/MF RL model - model_family: MEDIUM — ACT-R with IBL is not a standard model family in computational psychiatry; classified based on architectural description - eligibility_flag: MEDIUM — paper meets all four inclusion criteria but the nature of the computational model (ACT-R process model) and the confederate agents are atypical for this review
- **cannot_find:** - Exact model equations/formulas (referred to Juvina et al., 2015, 2019) - Fitted parameter values (not reported) - Number of free parameters in lesioned models (not specified) - Supplement (no supplement file found; paper appears to have no supplementary materials)
- **other_notes:** This paper is primarily a behavioral/cognitive modeling study using the ACT-R cognitive architecture. The model is a process model that incorporates instance-based learning, sequence learning, and trust-specific accumulators — it is not a reinforcement learning or Bayesian model in the traditional sense. The trust and trust-invest accumulators are the key social mechanisms. The empirical contribution is the novel MATG paradigm and the demonstration that trust miscalibration (over-trust and under-trust) can serve adaptive functions under trust necessity. No supplement was found for this paper.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_social_info_search
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_C_exchange_interdependence
- tax_mod_active_interaction
- tax_mod_social_info_search
- tax_model_MB
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_cognitive_architecture
- tax_rr_model_family = cognitive_architecture
- tax_rr_param_decay
- tax_rr_param_social_weight
- tax_rr_primary_topic = trust
- tax_rr_secondary_topic = reputation_learning
- tax_rr_topic_reputation_learning
- tax_rr_topic_trust
- tax_topic_reputation_learning
- tax_topic_trust
