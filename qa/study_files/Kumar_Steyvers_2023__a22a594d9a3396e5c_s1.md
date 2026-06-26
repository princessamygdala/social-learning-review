# Kumar & Steyvers (2023)

- **study_id:** `a22a594d9a3396e5c_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Kumar, A. A., & Steyvers, M. (2023). Help me help you: A computational model for goal inference and action planning. In M. Goldwater, F. K. Anggoro, B. K. Hayes, & D. C. Ong (Eds.), *Proceedings of the 45th Annual Conference of the Cognitive Science Society*. Creative Commons Attribution 4.0 International License (CC BY).
- **citation_short:** Kumar & Steyvers (2023)
- **doi:** LOW confidence — not reported in the extracted text  ### CANNOT FIND  - DOI (not in extracted text; conference proceedings) - Mean fitted parameter values (stated as fit at participant level but values not reported) - Formal model comparison metric (BIC, AIC, etc.) - Parameter recovery results - Model recovery results - Standard effect sizes (Cohen's d, r, etc.) - Data/code availability links (beyond preregistration)  ### OTHER NOTES  - This is a CogSci 2023 conference proceedings paper (6 pages), not a full journal article. The computational framework is explicitly described as "preliminary." - The paper is preregistered at https://osf.io/q2p6b - No supplement file found. - The paper's primary contribution is a novel experimental paradigm for studying helping + a Bayesian pragmatic inference modeling framework. The modeling is promising but incomplete (only first moves modeled, no formal model comparison, no parameter reporting). - Affiliated institutions: Bowdoin College and University of California, Irvine.  ### RE_EXTRACT_FLAG: false  ### VERIFICATION NOTES  - Schema compliance: All required fields present. Fields without neuroimaging data marked N/A. - WC consistency: 4 models tested so Rule 2 = Yes is appropriate. No simulation-based recovery so Rules 5-6 = No. No formal model comparison metric so Rule 7 = Partial. - Learning mode: Source is social (other's actions), target is social (other's goals/mental states). Correctly tagged. - Model details: model_family = Bayesian pragmatic inference (mathematical form), model_class = inverse planning / goal inference (function). Distinct and appropriate. - Missing info flagged: Mean fitted parameters, DOI, effect sizes, and formal model comparison all flagged in cannot_find and concerns. - Eligibility: Flagged as borderline learning-vs-decision-making. Within-trial Bayesian updating about a fixed goal over a sequence of observed moves is arguable as temporal learning, but could also be classified as sequential inference/decision-making.
- **publication_type:** conference proceedings (peer-reviewed)
- **year:** 2023.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** laborate and help each other is consid- principalorhelperemploytoensurethatthegoalisachieved; ethinkingisbroadly perspective, if they see the aqua move, is that sufficient evi-; laborative manner? For example, as shown by the; ethatyouarepreparingforalong-distancemove; College UniversityofCalifornia,Irvine; etheycanconfidentlyassisttheprin-; ethegoaltothehelperthantheother,; ether inverse planning; emails: mark.steyvers@uci.edu, a.kumar@bowdoin.edu
- **code_url:** https://osf.io/q2p6b

## Computational level
- **study_focus:** Cooperative helping behavior through pragmatic inference and goal inference in a collaborative assistance game. Principals communicate secret goals through action selection; helpers infer goals from observed actions.
- **study_focus_short:** Cooperative helping behavior through pragmatic inference and goal inference in
- **learning_mode_description:** - Learning mode: Learning from observed actions of a cooperative partner about their hidden goal, in order to plan helpful actions   - Learning from:     - Source type (social): other (principal/partner)     - Source content (social): action/policy (block moves selected by principal)   - Learning about:     - Target type (social): other (principal/partner)     - Target content (social): state (mental state; goals/intentions)
- **task_description:** In a block-based grid divided into rooms, a principal is assigned a secret goal (e.g., move all blue blocks to room C) and makes moves to achieve it while communicating the goal through pragmatic action selection; a helper observes the principal's moves and can either pass or move a block to assist, inferring the goal from observed actions.
- **task_paradigm:** Cooperative helping task
- **players:** Multi-agent (dyad), asymmetric (principal and helper roles fixed within game)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Block-based grid with colored blocks (red, blue, green) in three rooms, each divided into two sub-rooms; 48 possible goals across 5 types (move, cover, uncover, clear, fill)
- **method:** online / behavioural
- **method_full:** Behavioural / online
- **main_result:** - Principals made significantly more useful moves than harmful or inconsequential moves (F(2,130) = 162.85) - Principals' useful first moves were significantly more pragmatic (lower rank) than chance (chi-squared(1, N = 1634) = 9.98) - Helpers passed their turn nearly 25% of the time, with over 40% passing on first move - Pragmatic principal model assigned lower ranks to empirical moves than baseline model (t(1419.33) = -18.08) - Careful helper model better captured passing behavior; significant model x move type interaction (chi-squared(3, N = 1600) = 300.53)
- **effect_size:** LOW confidence — no standard effect sizes reported; only F, t, and chi-squared statistics
- **learning_from:** Other (principal's block moves/actions); social; observed action sequences that communicate underlying goal
- **learning_about:** Other's goals/intentions (principal's secret goal); social; mental state inference  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** MEDIUM confidence — described as "preliminary"; no formal winning model selection via standard criteria
- **model_family:** Bayesian
- **model_class:** Other
- **all_models_tested:** - {"name": "Baseline principal", "family": "Utility maximization (softmax)", "n_params": 1, "metric": "qualitative + simulation comparison"} - {"name": "Pragmatic principal", "family": "Bayesian pragmatic inference (recursive)", "n_params": 1, "metric": "qualitative + simulation comparison"} - {"name": "Baseline helper", "family": "Bayesian goal inference + utility maximization", "n_params": 1, "metric": "qualitative + simulation comparison"} - {"name": "Careful helper", "family": "Bayesian goal inference + probabilistic passing", "n_params": 2, "metric": "qualitative + simulation comparison"}
- **model_mb_mf:** MB (model-based; agents maintain explicit models of goal space and use inverse planning)
- **model_params:** MEDIUM confidence — parameters named and described but mean fitted values not reported
- **social_param:** α [S] — controls the careful helper's decision to pass vs. act based on the difference between the two most likely inferred goals; captures social uncertainty about the other agent's intentions. τ_p [S] — temperature for pragmatic principal's recursive reasoning about how moves communicate goals to the helper.
- **social_param_name:** α [S]
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** LOW confidence — no formal metric; only qualitative/statistical comparison
- **how_model_fit:** Individual-level-fit (best-fitting parameters obtained at participant level, then simulated)
- **data_type_fit_to:** Choice behavior (first moves made by principals and helpers)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 160 (80 dyads); recruited from Amazon Mechanical Turk (Masters qualification) and university subject pool; 89 dyads completed, 9 excluded (incomplete games, too many moves), final N = 80 dyads (160 participants). 10 games per dyad = 800 total games.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low-moderate. Highly controlled grid-based paradigm with abstract stimuli (colored blocks). Non-verbal interaction only (no language). Online administration via nodeGame. Goals are artificial (move/cover/uncover/fill/clear blocks). The asymmetric helper-principal structure captures some real-world helping dynamics but is simplified.
- **eligibility_flag:** MEDIUM confidence — borderline learning paper; within-trial Bayesian goal inference could be classified as learning or as one-shot inference across a sequence of observations
- **concerns:** - No formal model comparison metric reported (no BIC, AIC, LOOIC, etc.) — models are compared only qualitatively and via simulation - Mean fitted parameter values not reported - Only first moves modeled; full game dynamics not captured - No parameter recovery or model recovery analyses - No posterior predictive checks - Effect sizes not reported in standard format (only test statistics) - Preprint/conference paper — may have a more complete published version
- **limitations_reported:** we hope to more carefully evaluate our model predictions for the entire duration of the game"; "it is also possible that helpers were unclear about the hypothesis/goal space, given the ill-defined problem space"; model evaluation limited to first moves only; framework described as "preliminary
- **limitations_categorized:** Limited model evaluation (first moves only); task simplicity; no full gameplay modeling; preliminary computational framework; no formal model comparison
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Partial
- **wc_rule8:** Partial
- **wc_rule9:** Partial
- **wc_rule10:** Partial
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_active_interaction
- rr_tax_mod_mentalizing_inference
- rr_tax_mod_multiplayer_live
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_C_exchange_interdependence
- tax_mod_action_observation
- tax_mod_active_interaction
- tax_mod_mentalizing_inference
- tax_mod_multiplayer_live
- tax_model_MB
- tax_model_bayesian
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_param_temperature
- tax_rr_primary_topic = mentalizing
- tax_rr_secondary_topic = cooperation
- tax_rr_topic_cooperation
- tax_rr_topic_mentalizing
- tax_topic_cooperation
- tax_topic_mentalizing
