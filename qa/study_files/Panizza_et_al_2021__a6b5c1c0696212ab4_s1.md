# Panizza et al. (2021)

- **study_id:** `a6b5c1c0696212ab4_s1`
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
- **study_focus:** Social conformity / norm salience learning — how observing others' prosocial or antisocial choices polarises one's own social attitude through norm learning and authority compliance.
- **study_focus_short:** Social conformity / norm salience learning
- **learning_mode_description:** - Learning mode: Learning from observing an agent's (computer/individual/group) resource allocation choices about how salient social norms are, leading to attitude polarisation   - Learning from:     - Source type (social): other (individual participant) / group (group of participants) — in human conditions; (non-social): computer — in computer condition     - Source content (social): action/policy (observed allocation choices of the agent)   - Learning about:     - Target type (social): self (own social attitude / norm adherence)     - Target content (social): state (mental state — norm salience; how strictly social norms are followed)
- **task_description:** Participants played a resource-allocation game choosing between a default allocation (100 points to self, 50 to an unknown other) and alternative allocations that could increase or decrease the other's earnings. Halfway through, they predicted and received feedback on choices made by an observed agent (computer, individual, or group), then continued making allocation choices.
- **task_paradigm:** Social allocation task
- **players:** Single agent (participant), single target (unknown other recipient); between-subjects observation of computer / individual / group agent. "Single agent (participant), multi-condition (observed agent: computer / individual / group of 5)
- **n_players:** small group (3-4)
- **partner_type:** computer (algorithmic)
- **stimuli:** Point allocations on a circumference (prosocial and antisocial alternatives vs. default allocation), binary choice feedback from observed agent
- **method:** behavioural
- **method_full:** behavioural (lab-based)
- **main_result:** - Main Results:   - Attitude convergence significant in Computer (r = .43 [.23, .63], BF+0 = 786.20), Individual (r = .57 [.41, .75], BF+0 > 10000), and Group conditions (r = .58 [.43, .72], BF+0 > 10000), but not Baseline (r = .01, BF01 = 12.32)   - Significant effect of condition on attitude convergence (Kruskal-Wallis χ²(3) = 42.22, ε² = .11 [.07, .19])   - After removing compliant participants, Computer condition effect weakened (r = .30, BF+0 = 6.27) and no longer differed from Baseline (BF10 = 1.08)   - Compliance × condition interaction significant only for Computer condition (β = 25.31 [14.75, 35.87], t = 4.70)   - Robust regression adjusted R² = .241 for full model with compliance interaction   - Variable Attitude model won model comparison (ΔDIC lowest)   - Norm elicitation: prosocial vs. antisocial participants had significantly different appropriateness ratings (all p < .004), supporting norm learning   - No evidence for norm uncertainty (67/72 BF tests favoured null); norm salience supported
- **effect_size:** r = .43–.58 for attitude convergence in experimental conditions; ε² = .11 for condition effect; ρ = .62 for compliance-κ correlation; adjusted R² = .241 for regression model
- **learning_from:** Other (individual / group agent) or computer; observed allocation choices and feedback on agent's decisions. Source: other / group / computer.
- **learning_about:** Own social attitude (norm salience — how strictly social norms are followed). Target: self (social attitude / norm adherence).  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** Variable Attitude model (full version): V(πy, πo) = πy + tan(α)·πo, with α ~ N(μ, σ), bias κ, error ε; all parameters estimated separately before/after manipulation. Choice via probit link function with error mixture.
- **model_family:** Utility / EV
- **model_class:** Utility maximization
- **all_models_tested:** 1. {"name": "Variable Attitude — full (both α and σ vary)", "family": "Utility/random preference (probit)", "n_params": 8, "metric": "DIC = 32997.4"} 2. {"name": "Variable Attitude — fixed attitude (α fixed)", "family": "Utility/random preference (probit)", "n_params": 6, "metric": "DIC > 32997.4"} 3. {"name": "Variable Attitude — fixed variability (σ fixed)", "family": "Utility/random preference (probit)", "n_params": 6, "metric": "DIC > 32997.4"} 4. {"name": "Stable Attitude — full (both α and τ vary)", "family": "Utility/softmax", "n_params": 8, "metric": "DIC > 32997.4"} 5. {"name": "Stable Attitude — fixed attitude (α fixed)", "family": "Utility/softmax", "n_params": 6, "metric": "DIC > 32997.4"} 6. {"name": "Stable Attitude — fixed variability (τ fixed)", "family": "Utility/softmax", "n_params": 6, "metric": "DIC > 32997.4"}  Note: Exact DIC values for non-winning models are shown in Figure 2 but not reported numerically in the text for all models.
- **model_mb_mf:** N/A (not RL)
- **model_params:** - α (social attitude / social value orientation) — estimated before and after manipulation; mean before: 20° (SD = 14°) prosocial, −22° (SD = 20°) antisocial - σ (attitude variability / choice consistency) — estimated before and after manipulation; σ_after < σ_before (p < .001 all conditions) - κ (bias parameter / authority compliance) — estimated before and after; mean κ_before = 1.14 [below compliance threshold], 11.48 [above threshold] [S] - ε (error parameter — probability of random response mistake)
- **social_param:** - α [S]: Social value orientation / social attitude — defines how much points for the other person are worth relative to own points; tan(α) is the exchange rate. - κ [S]: Bias/compliance parameter — captures tendency to choose alternatives regardless of value, associated with authority compliance (ρ = .62 with compliance index).
- **social_param_name:** κ
- **social_param_value:** 1.14
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** DIC (Deviance Information Criterion)
- **how_model_fit:** individual-level-fit (Hierarchical Bayesian Analysis with JAGS; 4 Markov chains, 100,000 iterations, 5,000 burn-in, thinning rate 4; MAP estimates)
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 369 (376 recruited, 7 excluded; age M = 22, SD = 2; 167 males). Conditions: Baseline ~132 (with 102-trial subsets), Computer = 74, Individual ~74, Group ~66 (last two conditions underpowered relative to target N = 90).
- **population_category:** healthy adults
- **population_age_range:** M=22 (SD=2)
- **ecological_validity:** Lab-based point allocation task with hypothetical "unknown other" — limited ecological validity. Between-subjects design prevents within-person comparison of mechanisms. Agent attitudes were experimentally controlled (extreme prosocial/antisocial), which is somewhat artificial. However, the norm elicitation task adds ecological grounding by measuring actual normative beliefs. Preregistered design.
- **eligibility_flag:** 
- **concerns:** - Between-subjects design limits direct comparison of mechanisms within individuals - Last two conditions (Individual, Group) did not reach pre-specified sample size (74 and 66 vs. target 90) - Agent attitude was fixed at extreme values, confounding social distance with attitude change - Exact DIC values for non-winning models not reported numerically in text (only shown in figure) - Model does not include a learning/updating component per trial — attitude is estimated as a static parameter per phase (before/after), not as a trial-by-trial learning process. This raises questions about whether this constitutes "learning over time" in the strict sense, though attitude does change across phases.
- **limitations_reported:** Between-subjects design does not allow direct comparison of manipulations or exclude possibility of multiple simultaneous mechanisms; sample size in last two conditions fell short of pre-specified target for 0.95 power; fixed agent attitude means social distance from agent and attitude change are correlated; Individual and Group conditions did not differ as predicted by norm learning hypothesis, possibly because group size was not disclosed; group members were strangers with no shared identity, which may have weakened group influence; norm elicitation task cannot measure norm salience directly; implicit assumption that norms elicited in Computer condition were not influenced by computer prediction task.
- **limitations_categorized:** limited ecological validity; between-subjects design; sample size; confound between social distance and attitude change; limited manipulation of group features; measurement limitations (norm salience); task simplicity
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** Partial
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `all_models_tested` / n_params: MEDIUM — exact parameter counts inferred from model descriptions (full models have α_before, α_after, σ_before, σ_after or τ_before, τ_after, κ_before, κ_after, ε = ~8 individual-level params; reduced models fix one pair) - `wc_guidelines` rule 3: MEDIUM — supplementary analyses S1 and S2 suggest simulation work but details not fully visible in main text - `wc_guidelines` rule 5: MEDIUM — parameter recovery for δ_diff mentioned (S2) but not for all individual parameters - `learning_mode` / learning about: MEDIUM — classified as norm salience learning based on authors' conclusion, but this is the result of hypothesis testing rather than a direct model component
- **cannot_find:** - Exact DIC values for all 6 models (only winning model DIC = 32997.4 reported; others shown in figure only) - Exact N per condition (approximate from text: Baseline largest, Computer = 74, last two ~74 and ~66) - Supplementary materials content (supplements referenced as S1–S7 but not accessible as separate files)
- **other_notes:** - This paper is primarily a hypothesis-testing study using cognitive models to distinguish between competing explanations of conformity, rather than a trial-by-trial learning model study. The "learning" occurs at the phase level (before vs. after manipulation) rather than as a dynamic updating process. - The winning model is a utility model with random preference, not a reinforcement learning or Bayesian updating model. It estimates static attitudes per phase rather than modeling the learning process itself. - Data and code available on OSF (osf.io/p5xq3). - Preregistration with amendments documented.
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
- spec_target = partly
- tax_domain_A_influence_transmission
- tax_domain_F_affective_moral
- tax_mod_action_observation
- tax_mod_instructed
- tax_model_utility
- tax_param_learning_rate
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
