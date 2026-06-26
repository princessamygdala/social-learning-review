# Zonca et al. (2021)

- **study_id:** `a089a484bca4fd63e_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Zonca, J., Vostroknutov, A., Coricelli, G., & Polonio, L. (2021). Timing of social feedback shapes observational learning in strategic interaction. *Scientific Reports*, *11*, 21972. https://doi.org/10.1038/s41598-021-01466-1
- **citation_short:** Zonca et al. (2021)
- **doi:** 10.1038/s41598-021-01466-1
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Behavioural economics / Economics
- **affiliations_raw:** etheless, in social settings we do not always have the possibility to be guided by others’ behavior and we; Department of Economics (MPE), Maastricht University, Maastricht, The Netherlands; laborative Technologies (CONTACT) Unit, Italian Institute of Technology, Genoa,; ether and how strategic sophistication can be enhanced to maximize; mitation when they received feedback before their decision; University of Southern California, Los Angeles, USA; School for Advanced Studies Lucca, Lucca, Italy; mitate blindly the observed actions with-; emails: joshua.zonca@iit.it
- **code_url:** 

## Computational level
- **study_focus:** Observational learning in strategic interaction; how timing of social feedback (before vs. after choice) shapes imitation vs. sophisticated learning in game-theoretic settings.
- **study_focus_short:** Observational learning in strategic interaction
- **learning_mode_description:** - Learning mode: Learning from observation of a successful player's choices to improve strategic sophistication in one-shot matrix games   - Learning from:     - Source type (social): other (model player — the best performer in the session)     - Source content (social): action/policy (the model's row choice in each game)   - Learning about:     - Target type (non-social): world (optimal strategic response to the artificial agent's fixed strategy)     - Target content (non-social): action/policy (level-2 best-response strategy)
- **task_description:** Participants played one-shot 3x3 normal-form matrix games against an artificial agent using a fixed level-1 strategy. Across three phases (Assessment, Observation with social feedback from the best-performing player, Re-assessment with new games), the timing of feedback (before or after choice) was manipulated between subjects to examine whether observational learning led to imitation or genuine strategic improvement.
- **task_paradigm:** Observational learning task
- **players:** Single agent (participant), single artificial counterpart (computer using level-1 strategy); social feedback from one model player (best performer in session). "Single agent (participant), single target (model player — best performer); artificial opponent
- **n_players:** single agent (1)
- **partner_type:** computer (algorithmic)
- **stimuli:** 3x3 payoff matrices (normal-form games), arrow feedback indicating model's choice
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Medium-sophistication players in Post-feedback treatment increased level-2 choices from Assessment to Re-assessment relative to No-feedback (B = 0.80, z = 2.82, p = .005) [interaction effect]   - Medium-sophistication players in Pre-feedback treatment showed imitation during Observation (B = 1.10, z = 4.72, p < .001) but no transfer to Re-assessment (B = 0.40, z = 1.44, p = .151)   - Low-sophistication players showed no learning transfer in any treatment (Post-feedback Re-assessment interaction: B = 0.04, z = 0.12, p = .908)   - High-sophistication players maintained performance with feedback; declined without feedback (No-feedback Re-assessment: B = -1.46, z = -4.94, p < .001)   - Dynamic learning in Observation phase for Medium-sophistication Post-feedback: trial order effect (B = 0.05, z = 3.60, p < .001); absent in Pre-feedback (B = 0.00, z = 0.05, p = .959)   - Proportion of level-2 choices almost perfectly correlated with game outcomes (r = 0.96)
- **effect_size:** - Main Results:   - Medium-sophistication players in Post-feedback treatment increased level-2 choices from Assessment to Re-assessment relative to No-feedback (B = 0.80, z = 2.82, p = .005) [interaction effect]   - Medium-sophistication players in Pre-feedback treatment showed imitation during Observation (B = 1.10, z = 4.72, p < .001) but no transfer to Re-assessment (B = 0.40, z = 1.44, p = .151)   - Low-sophistication players showed no learning transfer in any treatment (Post-feedback Re-assessment interaction: B = 0.04, z = 0.12, p = .908)   - High-sophistication players maintained performance with feedback; declined without feedback (No-feedback Re-assessment: B = -1.46, z = -4.94, p < .001)   - Dynamic learning in Observation phase for Medium-sophistication Post-feedback: trial order effect (B = 0.05, z = 3.60, p < .001); absent in Pre-feedback (B = 0.00, z = 0.05, p = .959)   - Proportion of level-2 choices almost perfectly correlated with game outcomes (r = 0.96)
- **learning_from:** other (model player); the model's strategic choices in matrix games
- **learning_about:** world; optimal level-2 best-response strategy to the artificial agent's level-1 behavior  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** Cognitive Hierarchy (CH) model; Poisson distribution f(k) with single parameter τ describing mean level of strategic thinking. L = β₀ + β₁t + β₂p + β₃t*p + u₀ + ε (random effects logistic model for learning analysis)
- **model_family:** Economic strategy (EWA)
- **model_class:** Belief updating
- **all_models_tested:** [{"name": "Cognitive Hierarchy (CH)", "family": "Cognitive Hierarchy", "n_params": 1, "metric": "MLE (Poisson fit)"}, {"name": "Random effects logistic model (Models 1-4)", "family": "Logistic mixed-effects", "n_params": "varies (7 fixed + random intercept)", "metric": "robust standard errors"}, {"name": "Nash equilibrium", "family": "Game-theoretic equilibrium", "n_params": 0, "metric": "descriptive comparison"}, {"name": "Mixture models cluster analysis", "family": "Gaussian mixture model", "n_params": "not reported", "metric": "BIC (implied)"}]
- **model_mb_mf:** N/A (not RL; game-theoretic strategic reasoning model)
- **model_params:** - τ (tau): Poisson parameter for Cognitive Hierarchy model — mean and variance of the distribution of strategic thinking levels. Fitted values by cluster/treatment/phase:   - Low-soph Assessment: τ = 0.39; Re-assessment: τ = 0.86–0.97   - Medium-soph Assessment: τ = 1.15–1.34; Re-assessment: τ = 1.50–2.06   - High-soph Assessment: τ = 2.14–2.23; Re-assessment: τ = 1.87–2.29 - β₀, β₁ (treatment), β₂ (phase), β₃ (treatment × phase): fixed-effect regression coefficients in logistic models - u₀: random intercept (subject-level)
- **social_param:** τ is used to track social learning effects — changes in τ across phases reflect the impact of observational social feedback on strategic sophistication. The treatment × phase interaction coefficients (β₃) in the logistic models capture the social learning effect [S].
- **social_param_name:** τ is used to track social learning effects
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** The CH model is used descriptively (parameter estimation, not formal model comparison). Logistic models use robust standard errors with z-tests. Mixture model cluster analysis uses model-based clustering (Fraley & Raftery, 2002).
- **how_model_fit:** group-level-fit (CH τ estimated at cluster × treatment × phase level); individual-level random effects in logistic models
- **data_type_fit_to:** choice behavior (binary: level-2 consistent vs. inconsistent)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study only)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 321 (175 female; mean age 21.16, SD 2.01); main analyses on N = 301 after excluding models. Pre-feedback N = 136, Post-feedback N = 139, No-feedback N = 47. Three clusters: Low-sophistication N = 111, Medium-sophistication N = 111, High-sophistication N = 79.
- **population_category:** healthy adults
- **population_age_range:** M=21.16
- **ecological_validity:** Low-to-moderate. Uses abstract one-shot 3x3 matrix games with an artificial agent, not naturalistic social interaction. The "model" player is a real participant but feedback is limited to a single arrow indicating their choice. No face-to-face interaction. However, the between-subjects manipulation of feedback timing has ecological relevance to real-world learning contexts (e.g., educational settings, mentoring).
- **eligibility_flag:** Possible flag — the Cognitive Hierarchy model is used descriptively to characterize strategic levels rather than as a computational model of learning per se. The logistic regression models test for learning effects but are statistical models, not process models of learning. No formal computational model of the learning mechanism (e.g., reinforcement learning, Bayesian updating) is fitted. The paper describes observational learning but does not implement a computational model of the learning process itself. FLAG: borderline — uses computational models to characterize strategic sophistication and measure learning effects, but does not model the learning mechanism computationally. `eligibility_flag: "Borderline — CH model characterizes strategic levels descriptively; logistic regressions test learning effects statistically; no computational process model of the learning mechanism itself (e.g., no RL model, no Bayesian updating model fitted to trial-by-trial learning)"`
- **concerns:** - The CH model is used descriptively at the group level to track τ changes, not fitted as a trial-by-trial learning model - No computational model of the learning mechanism (no prediction error model, no Bayesian updating) - No-feedback treatment has substantially fewer participants (N = 47) than Pre-feedback (N = 136) or Post-feedback (N = 139), creating unbalanced design - Cluster analysis on Assessment phase choices, then testing learning within clusters, risks regression to the mean effects (acknowledged by authors for Low-sophistication cluster) - No individual-level parameter recovery for the CH model - Games in Re-assessment phase were structurally similar to Assessment games (payoffs shifted by a constant), which may limit claims about generalization
- **limitations_reported:** Authors acknowledge: regression to the mean may explain modest improvement in Low-sophistication No-feedback group; feedback at end of Assessment phase (informing participants they were not the best) may have influenced subsequent behavior; ceiling effects in High-sophistication cluster prevent detection of learning; the study is limited to one-shot games with an artificial agent and the model's feedback is restricted to a single choice indicator; the study does not investigate neural mechanisms; code available only upon request rather than publicly shared.
- **limitations_categorized:** potential regression to the mean; unbalanced group sizes; ceiling effects; limited ecological validity; no neuroimaging; limited data/code sharing; no computational process model of learning; task simplicity
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Partial
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** No
- **wc_rule9:** Partial
- **wc_rule10:** Partial
- **wc_score:** 2.5
- **wc_total:** 2.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `eligibility_flag` (MEDIUM): Borderline inclusion — no computational process model of learning mechanism; CH model used descriptively - `model_family` (MEDIUM): CH is a model of strategic reasoning, not a learning model per se; logistic regression is a statistical model - `winning_model` (LOW): No single "winning model" in the typical sense; CH used for characterization, logistic models for hypothesis testing - `social_param` (MEDIUM): τ tracks social learning effects indirectly; treatment × phase interactions are the actual social learning parameters
- **cannot_find:** - No trial-by-trial computational learning model (e.g., RL, Bayesian) — the paper does not fit one - No formal model comparison between competing learning models - No parameter recovery analysis - No model simulations - No effect sizes in standard formats (Cohen's d, η²) — results reported as logistic regression coefficients (B) and z-statistics
- **other_notes:** This paper is primarily a behavioral game theory study examining observational learning through the lens of the Cognitive Hierarchy model and logistic regression. It references computational models of social learning (prediction error, action prediction error) in the introduction but does not implement them. The key contribution is the behavioral finding that timing of social feedback differentially promotes imitation vs. sophisticated learning depending on initial strategic sophistication level. Data are publicly available on OSF. The study was conducted at the University of Trento with ethical approval.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = structural
- spec_locus = source
- spec_source = social
- spec_target = partly
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_mod_vicarious_outcome
- tax_model_bayesian
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_economic_strategy
- tax_rr_model_family = economic_strategy
- tax_rr_param_PE_signal
- tax_rr_param_social_weight
- tax_rr_primary_topic = strategic_reasoning
- tax_rr_secondary_topic = imitation_emulation
- tax_rr_topic_imitation_emulation
- tax_rr_topic_strategic_reasoning
- tax_topic_imitation_emulation
- tax_topic_strategic_reasoning
