# Steixner-Kumar et al. (2022)

- **study_id:** `ac02bfcaa3344eedb_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Steixner-Kumar, S., Rusch, T., Doshi, P., Spezio, M., & Gläscher, J. (2022). Humans depart from optimal computational models of interactive decision-making during competition under partial information. *Scientific Reports*, 12, 289. https://doi.org/10.1038/s41598-021-04272-x
- **citation_short:** Steixner-Kumar et al. (2022)
- **doi:** 10.1038/s41598-021-04272-x
- **publication_type:** peer-reviewed journal
- **year:** 2022.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** mitations of the original Tiger Problem is that it was incapable of addressing multiagent contexts; Institute of Systems Neuroscience, University Medical Center Hamburg-Eppendorf, Hamburg, Germany; mitation we introduced the interactive Tiger Problem; Institute of Technology, Pasadena, CA, USA; University of Georgia, Athens, GA, USA; ether, this work provides a novel; College, Claremont, CA, USA; Department of; emails: s.steixner-kumar@uke.de, mspezio@scrippscollege.edu, glaescher@uke.de
- **code_url:** 

## Computational level
- **study_focus:** Interactive decision-making under partial observability; competition vs. cooperation; Theory of Mind in social planning
- **study_focus_short:** Interactive decision-making under partial observability
- **learning_mode_description:** - Learning mode: Learning from probabilistic physical and social observations about another agent's actions and intentions during competitive/cooperative interaction   - Learning from:     - Source type (social): other (dyadic partner)       - Source content (social): action/policy (probabilistic observations of other's actions — creaks 80% accurate)     - Source type (non-social): world       - Source content (non-social): outcomes (probabilistic growls about tiger location, 70% accurate)   - Learning about:     - Target type (social): other (dyadic partner)       - Target content (social): action/policy (predicting partner's next action — listen/open-left/open-right)     - Target type (non-social): world       - Target content (non-social): state (world state; tiger location behind doors)
- **task_description:** In the Interactive Tiger Task (ITT), dyads of participants each face two doors hiding a tiger or gold pot. On each round they predict the partner's action, choose to listen (gaining probabilistic cues about tiger location and partner's action) or open a door, with payoffs determined by joint actions under cooperative or competitive payout matrices.
- **task_paradigm:** Coordination game
- **players:** Multi-agent (dyad), asymmetric contexts (cooperative or competitive); each participant also completed a single-agent version (TT)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Two doors (tiger/gold pot), probabilistic auditory cues (growls for tiger location, creaks for partner's action), payout matrices (original and modified), color-coded self/other indicators (yellow/blue)
- **method:** EEG / hyperscanning / behavioural
- **method_full:** Behavioural (+ EEG hyperscanning recorded but not reported in this paper)
- **main_result:** - During competition, participants gathered less evidence (fewer listen actions) than I-POMDP optimal models and performed worse (d = 0.74 for L1H1, d = 1.06 for L1H2 total score comparisons) - During cooperation, participants matched L1H2 model performance (d = 0.02, n.s.) and outperformed L1H1 (d = −0.30) - Competition yielded fewer listen actions than cooperation (d = 0.82) - Cooperation yielded higher correct open actions than competition (d = 1.15) - Prediction accuracy was higher during cooperation vs. competition (d = 1.61) - Learning occurred across sessions: identical open actions increased during cooperation (interaction context x session F(2,244) = 3.69, p = 0.026) - Prediction accuracy correlated with identical actions (cooperative: r = 0.90; competitive: r = 0.76; z = −2.55, p < 0.05)
- **effect_size:** Competition vs. cooperation listen actions d = 0.82; correct open actions d = 1.15; prediction accuracy d = 1.61; participant vs. L1H1 competitive total score d = 0.74; participant vs. L1H2 competitive total score d = 1.06; original vs. modified TT listen actions d = 0.56; evidence difference d = 0.56; correct open actions TT d = 0.38; prediction accuracy-identical action correlation (coop r = 0.90, comp r = 0.76)
- **learning_from:** Other (dyadic partner); probabilistic observations of partner's actions (80% accurate social cues) + world; probabilistic observations of tiger location (70% accurate physical cues)
- **learning_about:** Other (dyadic partner); partner's action selection (listen/open-left/open-right) + world; tiger location behind doors  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** I-POMDP Level 1, Horizon 2 (L1H2): Interactive POMDP with Bayesian belief updating over physical and social states, quantal response equilibrium for action selection, planning horizon of 2 steps, Level 1 ToM (models partner as Level 0 agent). For single-agent: POMDP with Bayesian belief updating.
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** [{"name": "POMDP (single-agent)", "family": "POMDP", "n_params": "not specified", "metric": "simulate-and-compare"}, {"name": "I-POMDP L1H1", "family": "I-POMDP", "n_params": "not specified — Level 1, Horizon 1", "metric": "simulate-and-compare"}, {"name": "I-POMDP L1H2", "family": "I-POMDP", "n_params": "not specified — Level 1, Horizon 2", "metric": "simulate-and-compare"}]
- **model_mb_mf:** MB (model-based — the I-POMDP explicitly plans over a model of the environment and other agent)
- **model_params:** States S (Tiger Left, Tiger Right); Actions A (Listen, Open-Left, Open-Right); observation accuracy for physical cues (70%); observation accuracy for social cues (80%); ToM level (Level 0 or Level 1); planning horizon (1 or 2 steps); quantal response equilibrium function (sigmoid) for action selection; 1000 particles for interactive particle filter approximation. Note: No free parameters fitted to individual participants — models were used as normative benchmarks for simulate-and-compare.
- **social_param:** ToM Level [S]: recursive depth of modeling of the other agent's beliefs and actions (Level 1 = model of other as Level 0 agent); social observation accuracy [S]: 80% accurate cues about partner's actions
- **social_param_name:** ToM Level [S]
- **social_param_value:** 80
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Simulate-and-compare (no formal model fitting or model comparison metric; models simulated with participants' observation sequences and performance compared via t-tests and ANOVAs)
- **how_model_fit:** simulate-and-compare (models not fitted to data; used as normative benchmarks)
- **data_type_fit_to:** N/A (models not fitted; compared to choice behavior)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (EEG hyperscanning was recorded but not analyzed/reported in this paper)
- **contrast:** 
- **key_regions:** N/A (no neural analyses reported)
- **coordinates_peak:** N/A — no neuroimaging results reported in this paper
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** N = 182 total (58 original payout: 30 cooperative, 28 competitive; 124 modified payout: 62 cooperative, 62 competitive; 82 women in modified variant); ages mean 25.30 ± 3.73 (women, modified) and 24.88 ± 3.67 (men, modified)
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low-moderate; highly abstract task (two doors, tiger/gold) adapted from AI research; dyads seated next to each other but separated by partition; payout matrices more engaging in modified version but still artificial; no real social interaction beyond implicit coordination through task structure
- **eligibility_flag:** Borderline — models are used as normative benchmarks (simulate-and-compare) rather than fitted to participant data. No computational model is fitted to individual behavior. Learning occurs across sessions (Fig 14) but the primary analysis is about departure from optimal solutions, not learning dynamics per se. The paper involves social interaction and repeated learning, but the computational models are not learning models fitted to data — they are optimal planning solutions used for comparison.
- **concerns:** (1) No model is actually fitted to participant data — POMDP/I-POMDP models are used as normative benchmarks only; (2) EEG hyperscanning data was collected but not reported; (3) Learning is demonstrated across sessions but no computational model of learning is fitted; (4) The "learning" demonstrated is improvement across sessions rather than trial-by-trial belief updating captured by a fitted model; (5) Modified payout matrix was created post-hoc after pilot participants reported demotivation — potential demand characteristics; (6) Data not publicly shared at time of publication (promised to be shared on NSF CRCNS site after acceptance)
- **limitations_reported:** Future attempts to move from computationally optimal models to applications with human persons and groups should proceed with caution and with empirical behavioral data"; computational demand of I-POMDP requires approximation (interactive particle filter); limited to Level 1 ToM agents due to computational constraints; simplified task context compared to real-world social interaction; data availability pending
- **limitations_categorized:** computational constraints; limited ecological validity; task simplicity; limited ToM depth; data not shared; no model fitting to individual data
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Yes
- **wc_rule4:** No
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** No
- **wc_rule9:** Partial
- **wc_rule10:** Partial
- **wc_score:** 3.5
- **wc_total:** 3.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_params (MEDIUM): No free parameters in the traditional sense — model is a normative benchmark with fixed architecture; specific implementation details referenced to prior publications - winning_model (MEDIUM): "Winning" model is a misnomer — L1H2 is the best-performing normative benchmark, not a fitted model - eligibility_flag (MEDIUM): Borderline case — models are not fitted to data but are computational models of optimal behavior in social context; learning occurs but is not the primary modeling target - data_type_fit_to (HIGH): Explicitly N/A — models not fitted
- **cannot_find:** Exact I-POMDP equations (referenced to Gmytrasiewicz & Doshi, 2005 and Doshi, 2005); quantal response equilibrium function parameters; number of free parameters in each model; supplement content (supplement referenced in text but not available in papers folder)
- **other_notes:** This paper adapts the Tiger Problem from AI research to human participants. It is primarily about comparing human behavior to optimal computational solutions (POMDP/I-POMDP) rather than fitting learning models to behavior. The I-POMDP framework is a sophisticated Bayesian planning model that embeds Theory of Mind, but it is used prescriptively, not descriptively. EEG hyperscanning data was recorded but analysis is deferred to future papers. The supplement is referenced (e.g., "see Table s2 and s3 (supplement)") but no supplement file was found in the papers folder. Supplement not accessible.
- **re_extract_flag:** false (full text available; supplement not found but flagged)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_mentalizing_inference
- rr_tax_mod_multiplayer_live
- spec_context = social
- spec_depth = structural
- spec_locus = source+target
- spec_source = partly
- spec_target = partly
- tax_domain_B_inference_modelling_others
- tax_domain_C_exchange_interdependence
- tax_mod_active_interaction
- tax_mod_mentalizing_inference
- tax_mod_multiplayer_live
- tax_model_MB
- tax_model_bayesian
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_primary_topic = strategic_reasoning
- tax_rr_secondary_topic = competition
- tax_rr_topic_competition
- tax_rr_topic_strategic_reasoning
- tax_topic_competition
- tax_topic_strategic_reasoning
