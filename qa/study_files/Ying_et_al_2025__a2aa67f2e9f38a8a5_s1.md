# Ying et al. (2025)

- **study_id:** `a2aa67f2e9f38a8a5_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Ying, L., Truong, R., Tenenbaum, J. B., & Gershman, S. J. (2025). Adaptive social learning using theory of mind. *Proceedings of the Annual Meeting of the Cognitive Science Society (CogSci 2025)*.
- **citation_short:** Ying et al. (2025)
- **doi:** Not reported in paper. Preprint arXiv:2507.09490 (based on arXiv identifier visible in text).
- **publication_type:** conference paper (peer-reviewed conference proceedings — cogsci 2025)
- **year:** 2025.0
- **field_of_study:** Psychology
- **affiliations_raw:** ethesetrade-offsastheydecidewhentoengageinso-; etheirexpertise,maynotalwaysoutweighthecost,; InstituteofTechnology,Cambridge,MA,USA; etheobservercaninferwhohasknowledge; University,Cambridge,MA,USA; etheirgoalsmoreefficiently; etheseheuristicscanbe; etheotheragent
- **code_url:** 

## Computational level
- **study_focus:** Adaptive social learning — how humans balance social learning (observing others) vs. non-social learning (self-exploration) using Theory of Mind to estimate the relative utility of each strategy.
- **study_focus_short:** Adaptive social learning
- **learning_mode_description:** - Learning mode: Learning from observing another agent's goal-directed navigation to infer environmental states (which wizard has the amulet), then using that information for one's own planning.   - Learning from:     - Source type (social): other (NPC agent / expert blue agent)     - Source content (social): action/policy (observed navigation trajectory)   - Learning about:     - Target type (non-social): world (environmental state — which wizard holds the amulet)     - Target content (non-social): state (world state — amulet location)
- **task_description:** In a two-player treasure hunt game, participants (red agent) must find a hidden object (amulet from a wizard) to pass a barrier and reach a goal treasure chest. At each step, participants choose to either observe an expert NPC (blue agent) for one step at low cost, or move themselves at higher cost.
- **task_paradigm:** Observational learning task
- **players:** Single agent (participant), single target (NPC expert agent)
- **n_players:** single agent (1)
- **partner_type:** computer (algorithmic)
- **stimuli:** Grid-world maze with treasure chests (A, B, C), colored barriers (red, blue), wizards; 54 stimuli (27 maps x 2 goal variants)
- **method:** online / behavioural
- **method_full:** Behavioural (online)
- **main_result:** - Rational Mentalizing model correlated strongly with human observing behavior (r = 0.83, 95% CI [0.68, 0.98]) - Social Mentalizing model: r = 0.28, 95% CI [0.02, 0.54] - Rational Non-Mentalizing model: r = 0.20, 95% CI [-0.06, 0.47] - Naive Observer model: r = -0.16, 95% CI [-0.42, 0.11] - Rational Mentalizing model matched human average steps (37.24 vs 37.89) and cost (76.72 vs 77.43)
- **effect_size:** r = 0.83 (95% CI [0.68, 0.98]) for Rational Mentalizing model vs. human behavior; split-half human reliability r = 0.80
- **learning_from:** Other (expert NPC agent); observed goal-directed actions/trajectory
- **learning_about:** World; environmental state (which wizard has the amulet)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Rational Mentalizing model (Bayesian ToM + utility maximization; β temperature parameter; A* planner)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** - {"name": "Rational Mentalizing", "family": "Bayesian ToM + utility maximization", "n_params": "1 (β)", "metric": "correlation with human behavior (r)"} - {"name": "Social Mentalizing", "family": "Bayesian ToM (no utility comparison)", "n_params": "1 (β)", "metric": "r"} - {"name": "Rational Non-Mentalizing", "family": "Utility maximization (no ToM)", "n_params": "1 (β)", "metric": "r"} - {"name": "Naive Observer", "family": "Heuristic (observe until interaction)", "n_params": "0", "metric": "r"}
- **model_mb_mf:** MB (model-based — uses forward simulation of other agent's plans via A* search)
- **model_params:** - β (action optimality / softmax temperature) — no fitted value reported - Observation cap: 15 steps per trial (fixed, not fitted) - Cost function C(Obs) vs C(Act) — not explicitly parameterized beyond game design
- **social_param:** Bayesian ToM inference over other agent's goal P(g_o) — the mentalizing component that infers the other agent's goals and beliefs from observed actions (Eq. 7), enabling estimation of the utility of social learning.
- **social_param_name:** Bayesian ToM inference over other agent's goal P
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Pearson correlation (r) between model predictions and human observing behavior (number of observe steps per game level); also average steps and average cost comparison.
- **how_model_fit:** simulate-and-compare (model simulations compared to human behavior at the aggregate level per game map)
- **data_type_fit_to:** Choice behavior (number of observation steps per trial)

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A (no neuroimaging)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 222 recruited (16 excluded for score below 0), final N = 206; mean age = 37.32; 119 female, 99 male, 2 non-binary, 2 others. Online (Prolific).
- **population_category:** healthy adults
- **population_age_range:** M=37.32
- **ecological_validity:** Low-moderate. Grid-world maze game is abstract and simplified. The observed agent is an NPC with full knowledge (expert), which is unrealistic. Only two agents; real-world social learning involves multiple agents with varying expertise. However, the task does capture the core trade-off between social and non-social learning.
- **eligibility_flag:** Potential flag — the paper models the *decision* to engage in social learning (observe vs. explore) rather than learning that updates over time in a traditional sense. The "learning" is more about information gathering for planning than iterative belief updating from repeated feedback. However, the model does involve Bayesian belief updating over time as observations accumulate (Eq. 3, 7), so it qualifies as learning over time. Flag: borderline learning-vs-decision-making.
- **concerns:** - No formal model comparison metric (BIC, AIC, etc.) — only correlation with aggregate behavior reported - β parameter value not reported; no individual-level fitting - Model comparison is at aggregate level (mean observe steps per map) rather than trial-by-trial individual choices - No parameter recovery or model recovery analyses - The observed agent is always an expert with full knowledge — limits generalizability - 16 participants excluded but exclusion criteria (score below 0) is somewhat arbitrary
- **limitations_reported:** (1) Game setup is quite simple; real-world decisions to engage in social vs non-social learning may be influenced by contextual and idiosyncratic factors such as individual propensity to observe; (2) Observed agent has full knowledge of the maze, which is often not true in human social learning; (3) Only one expert agent included; real social environments involve multiple agents or groups with diverging interests, expertise, and goals.
- **limitations_categorized:** Task simplicity; limited ecological validity; limited generalizability; single social partner; artificial expertise assumption
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** No
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Partial
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.0
- **wc_total:** 5.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - β fitted value: not reported (LOW confidence — parameter value not given) - n_params: Only β mentioned explicitly; cost function details unclear (MEDIUM) - Model comparison: No formal statistical model comparison (BIC/AIC/etc.) — only correlation reported (MEDIUM)  ---  ### IMPLEMENTATION LEVEL
- **cannot_find:** - DOI (not provided in paper; conference proceedings DOI may not yet exist) - β parameter fitted value - Individual-level model fits - Formal model comparison statistics (BIC/AIC/LOOIC) - Data/code availability statement
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- rr_tax_mod_social_info_search
- spec_depth = structural
- spec_locus = source+target
- spec_source = social
- tax_domain_A_influence_transmission
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_mod_social_info_search
- tax_model_MB
- tax_model_bayesian
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_mentalizing
- tax_rr_topic_social_info_use
- tax_social_nonsocial_comparison
- tax_topic_mentalizing
- tax_topic_social_info_use
