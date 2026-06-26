# Guilbeault et al. (2025)

- **study_id:** `a5894b4a391e9517f_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Guilbeault, D., Caplan, S., & Yang, C. (2025). A simple threshold captures the social learning of conventions. *Proceedings of the National Academy of Sciences* (preprint).
- **citation_short:** Guilbeault et al. (2025)
- **doi:** Not reported in the text (preprint; no DOI visible).
- **publication_type:** preprint (explicitly stated: "this is a preprint" on line 91)
- **year:** 2025.0
- **field_of_study:** Psychology
- **affiliations_raw:** SchoolofBusiness,StanfordUniversity;bLinguisticsProgram,CUNYGraduateCenter;cCognitiveScienceProgram,CUNYGraduateCenter;; DepartmentofLinguistics,UniversityofPennsylvania;eDepartmentofComputerandInformationScience,UniversityofPennsylvania; ethroughoutthecognitiveandsocialsciencesis quality of greeting gestures, such as handshaking or bowing;; ethisthresholdusingtheTolerancePrinciple,aparameter-; mitation mechanism often leaves under-specified; ethisthresholdusingtheTolerancePrinciple(TP),; mpirical grounding in research on; mits the ability to posit or; emails: scaplan@gc.cuny.edu, ycharles@upe
- **code_url:** https://github.com/scaplan/name-game

## Computational level
- **study_focus:** Social convention learning — how individuals learn and converge on shared behavioral conventions (e.g., names, coordination choices) from sparse, noisy behavioral data in social networks, using a threshold-based satisficing mechanism rather than optimization or imitation.
- **study_focus_short:** Social convention learning
- **learning_mode_description:** - Learning mode: Learning from others' coordination choices about which behavioral convention to adopt   - Learning from:     - Source type (social): other (network partners / dyadic partner)     - Source content (social): action/policy (observed name or color choices of partners across rounds)   - Learning about:     - Target type (social): group (shared convention among network members)     - Target content (social): action/policy (which name/color convention to adopt for coordination)
- **task_description:** *Study 1 (Name Game)*: Participants in fully-connected social networks (N=24, 48, or 96) are randomly paired each round to independently type a name for a target face; they receive monetary reward for matching and a penalty for mismatching, over dozens of rounds until a convention emerges. A follow-up introduces confederate minorities to test convention change via tipping points. *Study 2 (Mind-reading Game)*: Individual participants observe a simulated partner's binary color choices (red/blue) across a sequence of rounds with experimentally controlled noise levels, and must infer the partner's preferred coordination choice.
- **task_paradigm:** Coordination game
- **players:** *Study 1*: Multi-agent (fully-connected network of 24, 48, or 96 participants), symmetric; plus confederate-injection conditions with committed minorities. *Study 2*: Single agent (participant), dyadic (simulated partner).
- **n_players:** network (5+)
- **partner_type:** confederate
- **stimuli:** *Study 1*: Human face image, text-entry names, binary coordination feedback (match/mismatch + monetary payoff). *Study 2*: Binary color choices (red/blue), round-by-round feedback on match/mismatch with monetary rewards.
- **method:** online / behavioural
- **method_full:** Behavioural / online (Prolific for Study 2; lab-based for Study 1 from prior experiments)
- **main_result:** - Main Results:   - TP model predicts participants' next-round convention choice with 87.9% accuracy vs. IM 81.1%, OP 75.2%, Luce 53.4% (Proportion Test, p < .00001, n = 8,893 trial-level observations)   - Before TP threshold reached, OP accuracy only 59.1% vs. TP and IM significantly higher (Proportion Test, p < .00001, n = 10,630)   - Pre-threshold correlation between name frequency in memory and probability of choice: r = 0.84 (Pearson, p < 2.2 x 10^-16)   - Regression discontinuity shows significant change in learning rate before vs. after TP threshold (p < .00001)   - TP reproduces empirical convergence rates (20-30 rounds) while IM and OP converge too fast (~14-17 rounds) and Luce too slowly   - Under tipping point dynamics, TP predicts next-round choice with 89% accuracy vs. IM 79%, OP 77%, Luce 53.9% (all p < .0001)   - Preregistered mind-reading game: TP is only model statistically indistinguishable from human data (p = 0.51, chi-squared = 0.42); TP error = 0.04 vs. 2/3rds 0.07, Luce 0.12, OP 0.19   - TP outperforms 2/3rds threshold by 22.5 percentage points on average across diverging memory sizes (p < .0001)   - Post-threshold correlation of memory slot proportion to output: r = 0.94 (Pearson)
- **effect_size:** - Main Results:   - TP model predicts participants' next-round convention choice with 87.9% accuracy vs. IM 81.1%, OP 75.2%, Luce 53.4% (Proportion Test, p < .00001, n = 8,893 trial-level observations)   - Before TP threshold reached, OP accuracy only 59.1% vs. TP and IM significantly higher (Proportion Test, p < .00001, n = 10,630)   - Pre-threshold correlation between name frequency in memory and probability of choice: r = 0.84 (Pearson, p < 2.2 x 10^-16)   - Regression discontinuity shows significant change in learning rate before vs. after TP threshold (p < .00001)   - TP reproduces empirical convergence rates (20-30 rounds) while IM and OP converge too fast (~14-17 rounds) and Luce too slowly   - Under tipping point dynamics, TP predicts next-round choice with 89% accuracy vs. IM 79%, OP 77%, Luce 53.9% (all p < .0001)   - Preregistered mind-reading game: TP is only model statistically indistinguishable from human data (p = 0.51, chi-squared = 0.42); TP error = 0.04 vs. 2/3rds 0.07, Luce 0.12, OP 0.19   - TP outperforms 2/3rds threshold by 22.5 percentage points on average across diverging memory sizes (p < .0001)   - Post-threshold correlation of memory slot proportion to output: r = 0.94 (Pearson)
- **learning_from:** Other (network partners' or dyadic partner's coordination choices); social; observed actions/names/colors across rounds.
- **learning_about:** Group convention (which name or color to adopt for successful coordination); social; shared behavioral rule/convention.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Tolerance Principle (TP) threshold model — parameter-free: agent samples via Luce's Choice Axiom until a name occupies at least M - M/ln(M) memory slots, then deterministically produces that name. For M=12, threshold = 8/12.
- **model_family:** Heuristic
- **model_class:** Other
- **all_models_tested:** - {"name": "Tolerance Principle (TP)", "family": "Threshold/satisficing", "n_params": 0, "metric": "Prediction accuracy (% correct next-round choices)"} - {"name": "Optimization (OP)", "family": "Maximum likelihood / frequency maximization", "n_params": 0, "metric": "Prediction accuracy"} - {"name": "Imitation (IM)", "family": "Imitation / memory-deletion", "n_params": 0, "metric": "Prediction accuracy"} - {"name": "Luce (probability matching)", "family": "Luce Choice Axiom", "n_params": 0, "metric": "Prediction accuracy"} - {"name": "2/3rds rule", "family": "Fixed threshold", "n_params": 0, "metric": "Prediction accuracy"} - {"name": "Bayesian rule-learning", "family": "Bayesian belief updating", "n_params": 2, "metric": "Tipping point dynamics + convergence rates"}
- **model_mb_mf:** N/A (not RL; threshold-based satisficing model)
- **model_params:** - M (memory size): assumed = 12 (from prior work); robustness tested across 8-26. Not a free parameter of TP itself; held constant across models. - TP threshold = M - M/ln(M): parameter-free, deterministic function of M. For M=12, threshold = 8. - No free parameters in the TP model itself. - Bayesian model has 2 free parameters: P(Y) (prior for alternatives) and lambda (learning rate/smoothing). [Not the winning model.]
- **social_param:** The TP threshold is inherently social — it determines how much social information (observed partner behavior stored in memory) is "good enough" to adopt a convention. However, it is not a separable social parameter; the entire model concerns social learning.
- **social_param_name:** The TP threshold is inherently social
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Prediction accuracy (% correct next-round choices); convergence rate comparison to empirical data; absolute error from empirical convergence rates; regression discontinuity magnitude; Proportion Tests (two-sample); chi-squared tests.
- **how_model_fit:** Simulate-and-compare (agent-based model simulations using participants' actual interaction histories to predict next-round choices; also pure ABM simulations for convergence dynamics)
- **data_type_fit_to:** Choice behavior (round-by-round coordination choices)  ---  ### IMPLEMENTATION LEVEL

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
- **sample_size:** - Study 1 (Name Game): N = 264 participants across 6 initial trial networks (3 x 24, 2 x 48, 1 x 96) from Centola & Baronchelli (2015); plus 10 additional network trials from Centola et al. (2018) with confederates (networks of 20-30 people each). Total: 16 unique network trials. - Study 2 (Mind-reading Game): N = 800 recruited from Prolific (200 per condition x 4 conditions); 782 passed attention checks (attrition 2.25%).
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low-moderate. Both tasks are controlled laboratory/online coordination games using abstract stimuli (arbitrary names for faces; binary color choices). The name game removes extrinsic information such as normative valuation, sanctions, and intrinsic quality differences among options. The mind-reading game uses a simulated (not real) partner. The authors explicitly acknowledge these limitations and note the absence of normative valuation, social punishment, homophily, and other real-world features of convention formation.
- **eligibility_flag:** Potential concern — the paper does not use computational modeling in the typical reinforcement learning or Bayesian parameter-fitting sense. Instead, it compares parameter-free agent-based models (ABMs) via prediction accuracy. There is no individual-level parameter estimation. The "models" are deterministic decision rules applied to simulated memory, not fitted latent-variable models. This may be borderline for inclusion depending on how strictly "computational modeling" is defined. Additionally, the Study 1 behavioral data was collected by other researchers (Centola & Baronchelli, 2015; Centola et al., 2018) — the present paper reanalyzes it. Flag: borderline computational modeling (ABM comparison, no parameter fitting).
- **concerns:** - No individual-level parameter fitting — models are parameter-free ABMs compared on aggregate prediction accuracy. - Study 1 data is entirely from previously published experiments by other groups; only Study 2 is original. - Memory size M=12 is assumed (from prior work), not estimated from data. - The comparison models (IM, OP, Luce) may be overly simplistic straw-men; more sophisticated RL or Bayesian models with proper parameter estimation were not systematically tested. - The Bayesian model tested in the supplement uses a specific (and arguably narrow) implementation; the authors acknowledge other Bayesian formulations might perform differently. - No neural data; the authors themselves note that "verifying the functional form of the threshold at play will require future research with greater access to measurements of micro-level psychological processing, possibly through the inclusion of neuro-imaging data.
- **limitations_reported:** The TP is a mechanism for implicit learning with child language acquisition as a paradigmatic case; its application to social learning is appropriate for similar tasks such as the name game or the mind-reading game, which, by design, remove extrinsic information such as normative valuation or sanctions so as to isolate the cognitive process of rule-based pattern detection underlying conventionalization"; "both of the experiments we examine assume there are no intrinsic quality differences in the set of possible coordination behaviors, nor features of the social environment (such as public signals of perceived behavior quality)"; "a further limitation of our modeling approach to the name game is that we compare ABMs using a relatively small sample of experimental networks"; "the optimization view [...] the accelerating embrace of current AI methodologies (and LLMs specifically) as a framework for simulating human learning is likely to maintain this blind spot
- **limitations_categorized:** Limited ecological validity; task simplicity (no normative valuation, sanctions, or quality differences); small number of experimental networks; limited generalizability beyond coordination games; no neuroimaging data; memory size assumed not estimated.
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** No
- **wc_rule5:** 
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - `doi`: Not available in the text (preprint). MEDIUM confidence. - `eligibility_flag`: Borderline — ABM comparison without individual-level parameter fitting may not meet strict "computational modeling" criteria. MEDIUM confidence. - `winning_model`: The TP model is parameter-free (M is shared across all models and assumed, not fitted). HIGH confidence.
- **cannot_find:** - DOI (preprint, not yet assigned or not included in text) - Individual-level fitted parameter values (none exist; models are parameter-free) - No supplement as a separate file; supplementary materials are appended to the main paper text.
- **other_notes:** - This is a preprint (November 2025, PNAS format). - The paper bridges linguistics (Tolerance Principle from child language acquisition) and social learning/convention formation. - Study 1 behavioral data was collected by Centola & Baronchelli (2015) and Centola et al. (2018); the present paper contributes the TP model and model comparison framework. - The supplement is embedded within the main paper file (starts at "Supplementary Appendix" around line 872). - No supplement file found separately. - The paper compares 6 models total: TP, OP (optimization), IM (imitation), Luce (probability matching), 2/3rds threshold, and Bayesian rule-learning.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_cultural_network
- rr_tax_mod_experiential
- rr_tax_mod_multiplayer_live
- spec_context = social
- spec_depth = general
- spec_locus = source+target
- spec_source = social
- spec_target = partly
- tax_domain_A_influence_transmission
- tax_mod_cultural_network
- tax_mod_experiential
- tax_mod_multiplayer_live
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = heuristic
- tax_rr_model_heuristic
- tax_rr_param_decay
- tax_rr_primary_topic = norm_conformity
- tax_rr_secondary_topic = cultural_transmission
- tax_rr_topic_cultural_transmission
- tax_rr_topic_norm_conformity
- tax_topic_cultural_transmission
- tax_topic_norm_conformity
