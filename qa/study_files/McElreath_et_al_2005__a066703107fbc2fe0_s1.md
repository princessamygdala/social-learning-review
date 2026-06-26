# McElreath et al. (2005)

- **study_id:** `a066703107fbc2fe0_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** McElreath, R., Lubell, M., Richerson, P. J., Waring, T. M., Baum, W., Edsten, E., Efferson, C., & Paciotti, B. (2005). Applying evolutionary models to the laboratory study of social learning. *Evolution and Human Behavior*, *26*(6), 483-508.
- **citation_short:** McElreath et al. (2005)
- **doi:** 10.1016/j.evolhumbehav.2005.04.003
- **publication_type:** peer-reviewed journal
- **year:** 2005.0
- **field_of_study:** Anthropology / Cultural evolution
- **affiliations_raw:** section of the paper reviews the theory that motivates our experiments and lays; Department of EnvironmentalScienceandPolicy,UC Davis, Davis, CA95616, USA; Department of Anthropology, UCDavis, Davis, CA 95616, USA; mittingfrequency-dependentstrategieslikeconformity; mitate in ways that are not obviously profitable; mitation and other forms of social learning; ether one is interested in the; mity;Cultural evolution; emails: mcelreath@ucdavis.edu
- **code_url:** 

## Computational level
- **study_focus:** Social learning strategy selection -- how individuals regulate reliance on social vs. individual learning, including conformity, linear imitation, and confirmation strategies, as functions of task difficulty and environmental fluctuation.
- **study_focus_short:** Social learning strategy selection -- how individuals regulate reliance on
- **learning_mode_description:** - Learning mode: Learning from multiple peers' choice behavior (frequency information) about which option yields higher payoffs   - Learning from:     - Source type (social): group (all group members' choices)     - Source content (social): action/policy (group members' crop choices, frequency-based)   - Learning about:     - Target type (non-social): world (which crop is more profitable)     - Target content (non-social): state (world state; which option has higher mean)
- **task_description:** Participants repeatedly chose between two crops ("wheat" or "potatoes") across 20 seasons on each of 6 farms in a two-armed bandit task, receiving noisy yield feedback. Task difficulty (yield variance) and environmental fluctuation (probability of mean switching) were manipulated across farms. In Experiments 2 and 3, participants could optionally view the choices (but not payoffs) of one peer or all group members, respectively.
- **task_paradigm:** Two-armed bandit
- **players:** - Exp 1: Single agent (participant), no social targets - Exp 2: Single agent (participant), single anonymous peer observable (groups of 4-6) - Exp 3: Single agent (participant), multi-target (all group members observable; groups of 4-7)
- **n_players:** multi-target (3+)
- **partner_type:** human (live)
- **stimuli:** Abstract crop choice labels ("wheat"/"potatoes"), numerical yield feedback
- **method:** behavioural
- **method_full:** behavioural (laboratory microsociety experiment)
- **main_result:** - Exp 1: Memory Decay model best fits individual learning (best for 32/36 participants); choice sensitivity (b) decreases with higher yield variance and fluctuation - Exp 2: Evidence of both Linear Imitation (w = 0.78 in easy/no-fluctuation) and Confirmation (w = 0.99 in easy/fluctuation); social information access increases with variance, decreases with fluctuation - Exp 3: Evidence of both Linear Imitation (w = 0.99 in easy/no-fluctuation) and Conformity (w = 1.00 in easy/fluctuation); 38/49 participants best fit by Conformity when fluctuation present (sigma = 4) - Social learning reliance (a) generally higher in Exp 3 (0.12-0.54) than Exp 2 (0.04-0.42) - Effect sizes: D (goodness-of-fit relative to random) ranges from 0.07 to 0.42 across conditions; Akaike weights reported for all model comparisons (see Tables 2, 4, 5)
- **effect_size:** AIC-based model comparison with Akaike weights (w) and D (goodness-of-fit relative to random choice model); no Cohen's d, r, or other standardized effect sizes reported. Odds ratios for social information access: SD 0.5 OR = 0.852; Prob fluct 0 OR = 1.144 (Exp 2).
- **learning_from:** other (single peer, Exp 2) / group (all group members, Exp 3); observed crop choice behavior (actions)
- **learning_about:** world; which of two crops has higher mean yield  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** - Exp 1: Memory Decay (2 params: b, c) - Exp 2: Linear Imitation or Confirmation depending on condition (3 params: b, c, a) - Exp 3: Linear Imitation or Conformity depending on condition (3 params: b, c, a)
- **model_family:** Agent-based / evolutionary
- **model_class:** PE learning / Belief updating
- **all_models_tested:** - Exp 1: [{"name": "Bayes 1", "family": "Bayesian updating", "n_params": 1, "metric": "AIC"}, {"name": "Bayes 2", "family": "Bayesian updating (running mean)", "n_params": 1, "metric": "AIC"}, {"name": "Memory Decay", "family": "Parameterized exponential weighting", "n_params": 2, "metric": "AIC"}] - Exp 2: [{"name": "Memory Decay", "family": "Individual learning", "n_params": 2, "metric": "AIC"}, {"name": "Linear Imitation", "family": "Memory Decay + linear social", "n_params": 3, "metric": "AIC"}, {"name": "Confirmation", "family": "Memory Decay + confirmation social", "n_params": 3, "metric": "AIC"}] - Exp 3: [{"name": "Memory Decay", "family": "Individual learning", "n_params": 2, "metric": "AIC"}, {"name": "Linear Imitation", "family": "Memory Decay + linear social", "n_params": 3, "metric": "AIC"}, {"name": "Confirmation", "family": "Memory Decay + confirmation social", "n_params": 3, "metric": "AIC"}, {"name": "Conformity", "family": "Memory Decay + majority rule social", "n_params": 3, "metric": "AIC"}]
- **model_mb_mf:** MF (model-free; no internal model of environment, just weighted averaging of past yields)
- **model_params:** - b: choice sensitivity / inverse temperature (logit parameter); fitted values range 0.17-0.79 across conditions - c: memory decay weight on previous estimate vs. new observation; fitted values 0.00-0.21; when c = 0, only most recent yield matters - a [S]: reliance on social learning (0 = pure individual, 1 = pure social); fitted values 0.00-0.60 across conditions
- **social_param:** a -- weight of social information relative to individual learning in choice probability. Controls the mixture between individual Memory Decay model and social learning strategy (Linear Imitation, Confirmation, or Conformity).
- **social_param_name:** a
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC, Akaike weights (w), D (goodness-of-fit relative to random model)
- **how_model_fit:** group-level-fit (maximum likelihood across all individuals within each treatment condition; also individual-level fits reported for some comparisons)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Exp 1: N = 36 (+ 8 in motivation check session); Exp 2: N = 55 (12 groups of 4-6); Exp 3: N = 49 (9 groups of 4-7). All UC Davis undergraduates.
- **population_category:** undergraduates
- **population_age_range:** 
- **ecological_validity:** Low ecological validity. Abstract crop choice framing in a computerized two-armed bandit. Binary choice with numerical feedback. Social information limited to anonymous peer choices (no identity, payoff, or communication). Authors themselves note results need validation in naturalistic settings and that student samples are unrepresentative.
- **eligibility_flag:** 
- **concerns:** - No parameter recovery analysis - No model recovery / confusion matrix - No simulation-based model validation (simulations used for strategy comparison, not for checking model identifiability) - Group-level fitting may mask individual heterogeneity (acknowledged by authors) - No posterior predictive checks - Student sample (UC Davis undergraduates) -- generalizability concerns raised by authors - Experiment 1 has no social component; only Experiments 2 and 3 involve social learning - The Memory Decay model is quite simple and may miss structural features of learning (authors acknowledge this) - Small monetary incentives (~$6 average earnings)
- **limitations_reported:** results from laboratory studies like this one need to be validated in naturalistic or quasi-naturalistic settings"; "students in Western societies are repeatedly admonished to 'think for themselves'... Students in university are trained to learn in particular ways that are unlikely to be representative of most adults"; "parameter and strategy estimates from any one sample are notoriously prone to overfitting"; "these experiments obviously explore only a tiny fraction of the universe of meaningful learning environments and potential strategies available to people"; "we have the wrong models. All models are simplifications"; "many individuals never or almost never viewed social information
- **limitations_categorized:** limited ecological validity; limited generalizability (WEIRD student sample); overfitting risk; task simplicity; model misspecification risk; individual heterogeneity not fully modeled
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 6.0
- **wc_total:** 6.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - effect_size: MEDIUM -- only AIC/Akaike weights and D reported; no standardized effect sizes (Cohen's d, r, etc.) - model_class: MEDIUM -- classified as "prediction error learning / belief-weighted choice" but the Memory Decay model is not a standard PE model; it is a weighted average updating rule - model_mb_mf: MEDIUM -- classified as MF; the Memory Decay model updates estimates based on observed yields without a generative model of the environment, but "MF" is typically RL terminology and this is not strictly RL
- **cannot_find:** - Standardized effect sizes (none reported beyond AIC-based metrics and odds ratios) - Exact equations rendered poorly due to PDF-to-text conversion artifacts, but sufficient detail was extractable from context - No supplement available
- **other_notes:** - This is an early (2005) paper applying evolutionary/cultural evolution models to laboratory social learning -- predates much of the computational psychiatry literature - Three experiments, but only Experiments 2 and 3 involve social learning; Experiment 1 is individual learning baseline - The paper's primary contribution is testing evolutionary predictions about when people use social vs. individual learning, not fitting sophisticated computational models - No supplement found - The social learning models (Linear Imitation, Confirmation, Conformity) are nested within the individual learning model via the a parameter, allowing clean model comparison
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_experiential
- rr_tax_mod_social_info_search
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target+context
- spec_source = social
- tax_domain_A_influence_transmission
- tax_mod_action_observation
- tax_mod_experiential
- tax_mod_social_info_search
- tax_model_MF
- tax_model_bayesian
- tax_param_decay
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_agent_based_evolutionary
- tax_rr_model_family = agent_based_evolutionary
- tax_rr_param_decay
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = norm_conformity
- tax_rr_topic_norm_conformity
- tax_rr_topic_social_info_use
- tax_topic_norm_conformity
- tax_topic_social_info_use
