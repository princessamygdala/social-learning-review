# Panizza et al. (2021)

- **study_id:** `aca833a84ad094374_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Panizza, F., Vostroknutov, A., & Coricelli, G. (2021). How conformity can lead to polarised social behaviour. *PLoS Computational Biology*, *17*(10), e1009530. https://doi.org/10.1371/journal.pcbi.1009530
- **citation_short:** Panizza et al. (2021)
- **doi:** 10.1371/journal.pcbi.1009530
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Psychology
- **affiliations_raw:** University,Maastricht,theNetherlands,4DepartmentofEconomics,UniversityofSouthernCalifornia,Los; Institute sumeddemandsbytheauthority(verticalinfluence),orbecausetheylearnthatthe; UniversityofTrento,Mattarello(TN),Italy,3DepartmentofEconomics(MPE),Maastricht; ethisresearchhelpsuntanglingthebrainbasesandbehaviouralramificationsofpref-; ethepublicationof spiteful?Thisstudyexploredhowoursocialdecisionspolarise; Laboratory,IMTSchoolforAdvancedStudiesLucca,Italy,2CenterforMind/Brain; mity,itremainslargelyunclearwhyexactlypeopleshifttheirattitudeinthe; ethertopayforincreasing(prosocial)ordecreasing(a
- **code_url:** 

## Computational level
- **study_focus:** Social influence learning / norm conformity learning — how observing others' prosocial or antisocial choices polarises one's own social attitude, and whether this is driven by contagion, compliance, preference learning, or norm learning (norm salience).
- **study_focus_short:** Social influence learning / norm conformity learning
- **learning_mode_description:** - Learning mode: Learning from observed agent's prosocial/antisocial choices about the salience of social norms governing resource allocation   - Learning from:     - Source type (social): other (observed agent — individual, group, or computer depending on condition)     - Source content (social): action/policy (the agent's choices in the resource-allocation game)   - Learning about:     - Target type (social): social structure (social norms — how salient norm-following is)     - Target content (social): state (mental state; normative beliefs about social appropriateness)
- **task_description:** Participants repeatedly chose between a default allocation (100 points to self, 50 to an unknown other) and an alternative allocation that could be more prosocial or antisocial. Halfway through, they predicted the choices of an extremely prosocial or antisocial agent (computer, individual, or group), then resumed making allocation choices.
- **task_paradigm:** Social allocation task
- **players:** Single agent (participant), single-target (unknown other recipient); between-subjects manipulation of observed agent type (computer / individual / group of 5 / no agent baseline). N = 369 across 4 conditions.
- **n_players:** network (5+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Point allocations on a circumference (self vs. other trade-offs), binary choice (alternative vs. default allocation), feedback on prediction accuracy during manipulation phase.
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Participants polarised their social attitude toward the observed agent's extreme attitude across Computer, Individual, and Group conditions (all p < .001) but not Baseline (p = .457) - Attitude convergence in the Computer condition was driven by authority compliance (interaction: β = 25.31, t = 4.70, p < .001), not by contagion - After removing compliant participants, attitude convergence remained significant in Individual (r = .57) and Group (r = .55) conditions but weakened in Computer condition (r = .30) - No evidence for preference learning hypothesis (no differential increase in consistency between human vs. non-human conditions; BF_01 favoured null for most comparisons) - Norm elicitation showed prosocial and antisocial participants had different normative beliefs (all p < .004), supporting norm learning - No evidence for norm uncertainty (67/72 Bayes Factor tests favoured null); norm salience was the surviving explanation - Variable Attitude model (both α and σ vary) won model comparison (DIC_VA = 32997.4)
- **effect_size:** - Attitude convergence Computer condition: r = .43 [.23, .63], BF_+0 = 786.20 - Attitude convergence Individual condition: r = .57 [.41, .75], BF_+0 > 10000 - Attitude convergence Group condition: r = .58 [.43, .72], BF_+0 > 10000 - Baseline vs. Group: r = −.39 [−.51, −.27], BF_10 > 10000 - Compliance × Computer interaction: β = 25.31 [14.75, 35.87], t = 4.70 - Group condition main effect: β = 4.67 [3.29, 6.03], t = 6.67 - Individual condition main effect: β = 3.69 [1.89, 5.50], t = 4.011 - Compliance index vs. κ_before: ρ = .62 [.55, .67] - Model comparison adjusted R² = .241
- **learning_from:** Other (observed agent's choices in resource-allocation game — computer, individual, or group); source: other / group
- **learning_about:** Social norms (how salient norm-following is in the social context); target: social structure / norms  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** Variable Attitude model (full version): V(π_y, π_o) = π_y + tan(α) × π_o, with α ~ N(μ, σ); Pr(D=1) via probit link with threshold T_α; error parameter ε; bias parameter κ. Both α and σ estimated separately before/after manipulation.
- **model_family:** Utility / EV
- **model_class:** Utility maximization
- **all_models_tested:** [   {"name": "Variable Attitude (full: α varies, σ varies)", "family": "utility/random preference (probit)", "n_params": 8, "metric": "DIC"},   {"name": "Variable Attitude (fixed α, σ varies)", "family": "utility/random preference (probit)", "n_params": 6, "metric": "DIC"},   {"name": "Variable Attitude (α varies, fixed σ)", "family": "utility/random preference (probit)", "n_params": 7, "metric": "DIC"},   {"name": "Stable Attitude (full: α varies, τ varies)", "family": "utility/softmax", "n_params": 8, "metric": "DIC"},   {"name": "Stable Attitude (fixed α, τ varies)", "family": "utility/softmax", "n_params": 6, "metric": "DIC"},   {"name": "Stable Attitude (α varies, fixed τ)", "family": "utility/softmax", "n_params": 7, "metric": "DIC"} ]  Note on n_params: Each model has parameters estimated before/after manipulation. Full Variable Attitude model has: μ_before, μ_after (attitude centres), σ_before, σ_after (attitude variability), κ_before, κ_after (bias), ε_before, ε_after (error) = 8 subject-level parameters. Exact counts are inferred from the text.
- **model_mb_mf:** N/A (not RL; utility/value function model)
- **model_params:** - α (social attitude / social value orientation): angle parameter defining how much one point for the other is worth in terms of own points; tan(α) is the weight. Mean prosocial α_before ≈ 20° (SD = 14°), antisocial α_before ≈ −22° (SD = 20°). [S] - μ (centre of α distribution in Variable Attitude model): estimated before and after manipulation - σ (standard deviation of α distribution): represents variability/consistency in social attitude across choices; σ_after < σ_before in all conditions (p < .001) - κ (bias parameter): penalty/bonus points for default allocation; captures authority compliance. Non-compliant: κ_before = 1.14 [0.85, 1.43]; compliant: κ_before = 11.48 [8.78, 14.19]. [S — captures experimenter demand/authority compliance] - ε (error parameter): probability of random response/mistake in implementing choice - τ (temperature/noise in Stable Attitude models; NOT in winning model): softmax inverse temperature
- **social_param:** - α (social attitude / social value orientation): the angle defining how much the other's payoff matters relative to one's own; tan(α) converts other's points into own-point equivalents. [S] - κ (compliance bias): captures tendency to comply with authority/experimenter expectations by choosing alternative allocations regardless of prosocial/antisocial content. [S]
- **social_param_name:** α
- **social_param_value:** 14
- **social_param_sd:** 14
- **social_param_range:** 
- **model_comparison_metric:** DIC (Deviance Information Criterion)
- **how_model_fit:** individual-level-fit (Hierarchical Bayesian Analysis with subject-level and time-level parameters; JAGS with 4 Markov chains, 100,000 iterations, 5,000 burn-in, thinning rate of 4; MAP estimates)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

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
- **sample_size:** N = 369 (from 376 recruited; 4 excluded for software failures, 3 for prior pilot participation). By condition: Baseline (N ≈ 132), Computer (N = 74), Individual (N = 66), Group (N ≈ 97). Age M = 22, SD = 2; 167 males. Between-subjects design.
- **population_category:** healthy adults
- **population_age_range:** M=22 (SD=2)
- **ecological_validity:** Lab-based resource allocation task with abstract point allocations; participants never interact directly with the observed agent (indirect transmission only). Preregistered design. Limited ecological validity: abstract payoff structures, no face-to-face interaction, agent attitude was experimentally controlled. Authors note the paradigm could be applied to study conformity in other decision domains.
- **eligibility_flag:** 
- **concerns:** - Between-subjects design limits direct comparison across conditions - Some conditions underpowered (Individual: N = 66; Computer: N = 74) relative to pre-specified sample size of 90 - Agent attitude was fixed at extreme values (±45°), creating a correlation between social distance from agent and attitude change - The "Variable Attitude" model is not a standard learning model (no trial-by-trial update rule; attitude is estimated as a distribution over two blocks rather than tracked dynamically) - No trial-by-trial learning model (e.g., Rescorla-Wagner updating of norms); the computational approach is a measurement model rather than a process model of learning - Norm salience conclusion is reached by elimination rather than direct test
- **limitations_reported:** Between-subjects design does not allow direct comparison of manipulations or exclude multiple simultaneous mechanisms; some conditions did not reach pre-determined sample size for .95 power; fixed agent attitude means social distance from agent and attitude change are correlated, missing potential connection between initial similarity and conformity magnitude; attitude change in Individual condition was not significantly smaller than Group condition, possibly because participants were not informed about group size; norm elicitation task not designed to measure norm salience directly; Variable Attitude model could be improved by integrating both error types (comparison errors and attitude variability) under a common model, but this requires more trials or additional data types; default option may seem too unequivocal.
- **limitations_categorized:** limited ecological validity; between-subjects design limitations; sample size (underpowered conditions); task simplicity (fixed extreme agent); limited generalizability (social decisions only, not other preference domains); measurement limitation (norm salience inferred by elimination); model simplicity (no trial-by-trial learning dynamics)
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 8.0
- **wc_total:** 8.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `all_models_tested.n_params`: MEDIUM confidence — exact parameter counts per model inferred from text descriptions rather than an explicit table - `sample_size` breakdown by condition: MEDIUM confidence — Baseline N not explicitly stated (inferred from total minus other conditions) - `wc_guidelines.rule_3`: MEDIUM — S1 and S2 Analyses are referenced but not fully accessible (supplement .txt not found); partial credit given based on main text references to parameter recovery and model identification - `wc_guidelines.rule_8`: MEDIUM — robustness checks exist but no formal posterior predictive check described
- **cannot_find:** - Supplement files (S1–S7 Analyses, S1 Table, S1 Methods, S1 Fig) — not accessible as separate .txt files; referenced in main text but supplement file not found in papers folder - Exact DIC values for all 6 models (only winning model DIC = 32997.4 reported; others shown in Figure 2 as ΔDIC) - Exact N per condition for Baseline
- **other_notes:** - Supplement not accessible (no supplement file found in papers folder). Main text references S1–S7 Analyses and other supplementary materials but these could not be consulted. - The computational modelling here is primarily a measurement/estimation framework (estimating social attitude distributions before vs. after manipulation) rather than a trial-by-trial learning model. It does not include prediction error–based updating. The "learning" component is captured by comparing parameter estimates across task phases rather than by a dynamic learning algorithm. - This paper tests 5 competing hypotheses about social conformity (time-dependence, contagion, compliance, preference learning, norm learning) using between-subjects experimental conditions and cognitive modelling. The conclusion is that compliance to authority and norm salience learning are the two surviving explanations. - Data and code publicly available at osf.io/p5xq3.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_instructed
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_F_affective_moral
- tax_mod_action_observation
- tax_mod_instructed
- tax_model_utility
- tax_param_learning_rate
- tax_param_social_bonus
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = utility_EV
- tax_rr_model_utility_EV
- tax_rr_param_social_weight
- tax_rr_primary_topic = norm_conformity
- tax_rr_secondary_topic = prosocial_altruism
- tax_rr_topic_norm_conformity
- tax_rr_topic_prosocial_altruism
- tax_topic_norm_conformity
- tax_topic_prosocial_altruism
