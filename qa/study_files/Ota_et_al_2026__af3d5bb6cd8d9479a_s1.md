# Ota et al. (2026)

- **study_id:** `af3d5bb6cd8d9479a_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Ota, K., Christofilea, E., Charles, L., Daunizeau, J., & Haggard, P. (2026). Freedom through understanding: Instructed knowledge shapes voluntary action choices. *Royal Society Open Science*, *13*, 250845. https://doi.org/10.1098/rsos.250845
- **citation_short:** Ota et al. (2026)
- **doi:** 10.1098/rsos.250845
- **publication_type:** peer-reviewed journal
- **year:** 2026.0
- **field_of_study:** Psychology
- **affiliations_raw:** DepartmentofPsychology,CentreforBrainandBehaviour,SchoolofBiologicaland; ethodologicalchallengesofstudyingvolitioninvolvesenrichingtheexperi‑; InstituteofCognitiveNeuroscience,UniversityCollegeLondon,London,UK; etheypotentiallycombineboth‘freedomfromimmediacy’(i; ethertoactisanessentialattributeofthehumanmind; ethisarticle:OtaK,ChristofileaE,CharlesL,; ethedefiningfeaturesofhumanvoluntariness; etheiractionchoicestofindtherighttime; emails: k.ota@ucl.ac.uk
- **code_url:** 

## Computational level
- **study_focus:** Belief learning in competitive games; how instructed knowledge about a competitor's strategy shapes voluntary action choices and shifts between reinforcement learning, first-order belief learning, and second-order belief learning.
- **study_focus_short:** Belief learning in competitive games
- **learning_mode_description:** - Learning mode: Learning from competitive outcomes and opponent actions about one's own optimal action strategy to avoid interception by a virtual competitor   - Learning from:     - Source type (social): other (virtual competitor / "birds")       - Source content (social): action/policy (competitor's interception timing choices)     - Source type (non-social): self       - Source content (non-social): outcome (win/loss feedback)   - Learning about:     - Target type (social): other (virtual competitor)       - Target content (social): action/policy (competitor's likely future action / competitor's beliefs about participant's action)     - Target type (non-social): self       - Target content (non-social): action/policy (own optimal action timing strategy)
- **task_description:** Participants competed against a virtual opponent ("birds") in an online game where they chose when (early/middle/late) to deliver food to avoid interception. One competitor type (Competitor 1) monitored the participant's past 10 choices and predicted their most likely interval, punishing choice biases; participants had to innovate their action timing to avoid being predictable.
- **task_paradigm:** Matching pennies
- **players:** Single agent (participant), single opponent (virtual competitor algorithm); 3 between-subjects groups (control N=73, no instruction N=73, instruction N=73)
- **n_players:** network (5+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Animated game scene (tree, birds, basket with apples, food delivery), binary feedback ("Success!" / "Fail!" / "Timeout!")
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Both experimental groups reduced choice bias under competitive pressure (no instruction: z = 6.94, p < .001; instruction: z = 7.13, p < .001), while control group did not (z = 0.09, p = .93) - No instruction group shifted from RL to first-order belief learning (protected exceedance probability = 69.1% for 1st-order BL in test block) - Instruction group shifted from RL to second-order belief learning (protected exceedance probability = 88.7% for 2nd-order BL in test block) - No instruction group success rate decreased in test block (median = 62.0%, z = 3.95, p < .001); instruction group did not (median = 65.3%, z = 1.60, p = .11) - Instruction group showed significantly lower choice bias than no instruction group in test block (z = −5.20, p < .001) - Between-group model frequency difference was significant in test block (p < .001) but not baseline (p = .99) - Hybrid model (1st + 2nd order BL) best predicted instruction group test block data (from supplement)
- **effect_size:** - No instruction group: lag-1 correlation with opponent's action shifted from β = −0.33 (baseline) to β = −0.67 (test), z = 5.56 - Instruction group: lag-1 correlation with own action shifted from β = 0.23 (baseline) to β = −0.59 (test), z = 12.30 - Classification accuracy: RL baseline ~46–53%; 1st BL test (no instruction) = 41.4%; 2nd BL test (instruction) = 39.3%; hybrid test (instruction) = 40.4%
- **learning_from:** Other (virtual competitor's interception actions) and self (own win/loss outcomes)
- **learning_about:** Other (competitor's action strategy / competitor's beliefs about participant's own action) and self (own optimal action timing)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** - No instruction group (test block): First-order Belief Learning (1 α, 1 β, 1 ρ; softmax with temporal discounting) - Instruction group (test block): Second-order Belief Learning (1 α, 1 β, 1 ρ; softmax with temporal discounting); hybrid 1st+2nd order BL was best in supplementary analysis (2 α, 1 β, 1 ρ)
- **model_family:** Bayesian
- **model_class:** PE learning / Belief updating
- **all_models_tested:** [   {"name": "Pseudo-random", "family": "Random", "n_params": 0, "metric": "AICc + BMS"},   {"name": "Action alternation", "family": "Heuristic", "n_params": 3, "metric": "AICc + BMS"},   {"name": "Reinforcement Learning (RW)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "AICc + BMS"},   {"name": "First-order Belief Learning", "family": "Belief learning", "n_params": 3, "metric": "AICc + BMS"},   {"name": "Second-order Belief Learning", "family": "Belief learning", "n_params": 3, "metric": "AICc + BMS"},   {"name": "Hybrid 1st+2nd order BL", "family": "Belief learning (hybrid)", "n_params": 4, "metric": "Max log-likelihood (supplement)"} ]
- **model_mb_mf:** MB (belief learning models are model-based; RL model is MF)
- **model_params:** - α (learning rate; constrained 0–1): rate of belief/value updating. [S] in BL models — updates beliefs about opponent's actions or opponent's beliefs about agent's actions - β (temperature/choice consistency; constrained 0–20): scales decision consistency in softmax - ρ (temporal discounting; constrained 0–0.2): captures preference for earlier response intervals - λ (alternation rate; constrained 0–1; action alternation model only): scales tendency to alternate - α_1st, α_2nd (hybrid model only; both constrained 0–1): separate learning rates for 1st-order and 2nd-order belief processes [S]  Mean fitted values: Not explicitly reported as group means in text; parameter distributions shown in Supplementary Figure S1 (box plots).
- **social_param:** - α in 1st-order BL [S]: learning rate for updating beliefs about opponent's likely action - α in 2nd-order BL [S]: learning rate for updating beliefs about opponent's prediction of agent's own action - α_1st, α_2nd in hybrid model [S]: separate learning rates for 1st-order and 2nd-order belief updating processes
- **social_param_name:** α
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AICc (corrected for finite sample size) + protected exceedance probability from random-effect Bayesian model selection (BMS); supplementary analysis used maximum log-likelihood
- **how_model_fit:** individual-level-fit (parameters optimized individually per participant per block via MLE using Bayesian Adaptive Direct Search with 18 random restarts)
- **data_type_fit_to:** choice behavior (categorical choice among 3 time intervals: early/middle/late)  ---  ### IMPLEMENTATION LEVEL

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
- **sample_size:** N = 219 (73 per group: control, no instruction, instruction); UK-based; mean age ~30 years; recruited via Prolific
- **population_category:** healthy adults
- **population_age_range:** M=29.5
- **ecological_validity:** Online competitive game with animated stimuli provides ecological structure through competitive pressure and goal-directed action, but opponent is an algorithm rather than a real human; temporal choice is constrained to 3 discrete intervals; no real social interaction
- **eligibility_flag:** The "social agent" is an automated virtual competitor (algorithm), not a human — FLAG. The paper studies voluntary action/volitional control as a primary focus rather than social learning per se, though computational models of belief learning about a competitor are central. Learning does occur over time (trial-by-trial updating). Uses computational modeling with human behavioral data. Borderline: the primary research question is about volition/voluntary action rather than social learning, but the computational models explicitly capture social belief learning (mentalizing). FLAG as borderline social learning focus.
- **concerns:** - The virtual competitor is an algorithm, not a human agent — limits social validity of "belief learning" and "mentalizing" claims - Mean fitted parameter values not reported numerically (only box plots in supplementary figure S1) - No parameter recovery analysis - No model recovery / confusion matrix - No simulation-based validation before fitting - Classification accuracy is relatively low (39–53%), suggesting models explain limited variance - The paper's primary interest is volition/voluntary action rather than social learning mechanisms per se
- **limitations_reported:** The paper does not have a dedicated limitations section. From the discussion: "Our paradigm does not address all the aspects that might constitute volition"; "In our study, the goal is simple and pre-provided: to earn points. This does not capture the autonomy and diversity of human goal-setting and goal-pursuit outside the laboratory"; the competitor is a virtual algorithm rather than a real social agent (implicit limitation).
- **limitations_categorized:** limited ecological validity; task simplicity; no real social interaction (virtual competitor); limited generalizability of volition construct
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 7.0
- **wc_total:** 7.0

## Context flags
- **ctx_copresence:** no
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
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = social
- spec_depth = structural
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MB
- tax_model_MF
- tax_model_bayesian
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_social_weight
- tax_rr_primary_topic = strategic_reasoning
- tax_rr_secondary_topic = competition
- tax_rr_topic_competition
- tax_rr_topic_strategic_reasoning
- tax_topic_competition
- tax_topic_strategic_reasoning
