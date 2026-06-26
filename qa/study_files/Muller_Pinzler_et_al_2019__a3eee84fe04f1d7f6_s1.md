# Muller-Pinzler et al. (2019)

- **study_id:** `a3eee84fe04f1d7f6_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Muller-Pinzler, L., Czekalla, N., Mayer, A. V., Stolz, D. S., Gazzola, V., Keysers, C., Paulus, F. M., & Krach, S. (2019). Negativity-bias in forming beliefs about own abilities. *Scientific Reports*, *9*, 14416. https://doi.org/10.1038/s41598-019-50821-w
- **citation_short:** Muller-Pinzler et al. (2019)
- **doi:** 10.1038/s41598-019-50821-w
- **publication_type:** peer-reviewed journal
- **year:** 2019.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** Department of Psychiatry and Psychotherapy, Social Neuroscience Lab, University of Lübeck, Ratzeburger Allee; University of Amsterdam, Nieuwe Achtergracht 116, NL-1018 WV, Amsterdam, The Netherlands; Department of Psychiatry and Psychotherapy, Translational Psychiatry Unit (TPU),; University of Lübeck, Ratzeburger Allee 160, D-23538, Lübeck, Germany; school or acting more prosocially during the next social interaction); school performance (“Am I good at my job?”; “Am I a; Lab, Netherlands Institute; Department of Psychology,; emails: mueller-pinzler@snl.uni-luebeck.de
- **code_url:** 

## Computational level
- **study_focus:** Self-related ability belief updating; negativity bias in self-related learning modulated by self-esteem and social anxiety in social vs. private contexts
- **study_focus_short:** Self-related ability belief updating
- **learning_mode_description:** - Learning mode: Learning from manipulated performance feedback about one's own cognitive estimation abilities (and another person's abilities as control)   - Learning from:     - Source type (non-social): self       - In Exp 1 & 3, also: Source type (social): other (co-participant)     - Source content (non-social): outcome (performance feedback percentile)   - Learning about:     - Target type (non-social): self (own ability beliefs)       - In Exp 1 & 3, also: Target type (social): other (co-participant's ability beliefs)     - Target content (non-social): state (self-efficacy belief / ability estimate)
- **task_description:** Participants performed a cognitive estimation task (e.g., estimating weights of animals) and received manipulated relative performance feedback as percentiles compared to an alleged reference group. They continuously updated their expected performance ratings across trials in High Ability and Low Ability conditions, with some experiments including observation of another participant's performance or an evaluative audience.
- **task_paradigm:** Estimation / dot task
- **players:** Exp 1 & 3: Multi-agent (dyad), asymmetric (participant + co-participant taking turns); Exp 2: Single agent (participant), no partner (Private vs Public audience manipulation between-subjects)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Estimation questions (weights of animals, heights of houses), percentile performance feedback (numeric), category cues
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Self-related negativity bias: higher learning rates for negative vs positive PEs when learning about self, absent when learning about other (Agent x PE Valence interaction Exp 1: F(1,22) = 5.49, Exp 3: F(1,28) = 15.45)   - Cumulative Bayesian analysis across all 3 experiments: extremely high evidence for negativity bias (BF10 = 19081.7; delta = -0.68, 95% CI [-0.41, -0.95])   - Even with informed prior favoring positivity bias: BF10 = 94.4; delta = -0.36, CI [-0.18, -0.55]   - Self-esteem associated with valence bias (r(52) = 0.44, BF10 = 30.0)   - Social anxiety associated with negativity bias only in public context (r(58) = -0.39 public; r(50) = 0.06 private; z = 2.39)
- **effect_size:** - Agent x PE Valence interaction Exp 1: F(1,22) = 5.49 - Agent x PE Valence interaction Exp 3: F(1,28) = 15.45 - Cumulative negativity bias: delta = -0.68, 95% CI [-0.41, -0.95], BF10 = 19081.7 - Self-esteem correlation with valence bias: r = 0.44, BF10 = 30.0, delta = 0.44, CI [0.18, 0.63] - SIAS x Valence Bias (Public): r = -0.39, BF10 = 14.4, delta = -0.39, CI [-0.14, -0.58] - Model fit (winning model): R2 = 0.37 +/- 0.24
- **learning_from:** Self; performance feedback (manipulated percentile ranking) on own cognitive estimation performance. Also other (co-participant) in Exp 1 & 3.
- **learning_about:** Self; own ability beliefs (cognitive estimation ability). Also other (co-participant's ability) in Exp 1 & 3.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** - Exp 1 & 3 (Agent-LOOP): Valence Model with Self/Other distinction (Model 6): RW with 4 LRs (alpha_PE+(S), alpha_PE-(S), alpha_PE+(O), alpha_PE-(O)) + 4 initial value parameters - Exp 2 (Audience-LOOP): Valence Model (Model 3): RW with 2 LRs (alpha_PE+, alpha_PE-) + 2 initial value parameters - Formula: EXP(t+1) = EXP(t) + alpha * PE(t), where PE(t) = FB(t) - EXP(t); separate alpha for positive vs negative PEs (and self vs other in Agent-LOOP)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** Agent-LOOP (Exp 1 & 3): [   {"name": "Mean Model (M7)", "family": "Mean/baseline", "n_params": 4, "metric": "PSIS-LOO = -2953.6"},   {"name": "Unity Model, Self=Other (M1)", "family": "Rescorla-Wagner", "n_params": 5, "metric": "PSIS-LOO = -2380.1"},   {"name": "Ability Model, Self=Other (M2)", "family": "Rescorla-Wagner", "n_params": 6, "metric": "PSIS-LOO = -2336.5"},   {"name": "Valence Model, Self=Other (M3)", "family": "Rescorla-Wagner", "n_params": 6, "metric": "PSIS-LOO = -2320.5"},   {"name": "Unity Model, Self!=Other (M4)", "family": "Rescorla-Wagner", "n_params": 6, "metric": "PSIS-LOO = -2376.2"},   {"name": "Ability Model, Self!=Other (M5)", "family": "Rescorla-Wagner", "n_params": 8, "metric": "PSIS-LOO = -2330.7"},   {"name": "Valence Model, Self!=Other (M6) [WINNER]", "family": "Rescorla-Wagner", "n_params": 8, "metric": "PSIS-LOO = -2244.8, pxp = 0.998"} ] Audience-LOOP (Exp 2): [   {"name": "Mean Model (M4)", "family": "Mean/baseline", "n_params": 2, "metric": "PSIS-LOO = -1189.5"},   {"name": "Unity Model (M1)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "PSIS-LOO = -708.2"},   {"name": "Ability Model (M2)", "family": "Rescorla-Wagner", "n_params": 4, "metric": "PSIS-LOO = -570.2"},   {"name": "Valence Model (M3) [WINNER]", "family": "Rescorla-Wagner", "n_params": 4, "metric": "PSIS-LOO = -495.2, pxp > 0.999"} ] Note: Supplement reports additional models (M8-M19 for Agent-LOOP, M5-M10 for Audience-LOOP) with different initial value parameterizations; all lost to the winning models.
- **model_mb_mf:** MF
- **model_params:** - alpha_PE+(S) [S]: Learning rate for positive PEs about self. Exp 1: M = 0.12, SD = 0.06; Exp 3: M = 0.09, SD = 0.05 - alpha_PE-(S) [S]: Learning rate for negative PEs about self. Exp 1: M = 0.14, SD = 0.09; Exp 3: M = 0.15, SD = 0.10 - alpha_PE+(O): Learning rate for positive PEs about other. Exp 1: M = 0.11, SD = 0.08; Exp 3: M = 0.12, SD = 0.08 - alpha_PE-(O): Learning rate for negative PEs about other. Exp 1: M = 0.10, SD = 0.07; Exp 3: M = 0.11, SD = 0.07 - alpha_PE+ (Exp 2 only): Learning rate for positive PEs. Private: M = 0.07, SD = 0.06; Public: M = 0.06, SD = 0.06 - alpha_PE- (Exp 2 only): Learning rate for negative PEs. Private: M = 0.10, SD = 0.08; Public: M = 0.08, SD = 0.08 - Initial value parameters (IV) for each ability condition (fitted, values not individually reported)
- **social_param:** alpha_PE-(S) — learning rate for negative prediction errors about self; captures the self-specific negativity bias in belief updating. The asymmetry alpha_PE-(S) > alpha_PE+(S) indexes the negativity bias when learning about one's own abilities.
- **social_param_name:** alpha_PE+
- **social_param_value:** 0.12
- **social_param_sd:** 0.06
- **social_param_range:** 
- **model_comparison_metric:** PSIS-LOO (Pareto-smoothed importance sampling leave-one-out cross-validation) + Bayesian model selection (BMS) with protected exceedance probability (pxp) and Bayesian omnibus risk (BOR)
- **how_model_fit:** individual-level-fit (Bayesian MCMC via RStan; 3 chains, 2400 post-burn-in samples after 1000 burn-in, thinned by factor 3)
- **data_type_fit_to:** choice behavior (performance expectation ratings)  ---  ### IMPLEMENTATION LEVEL

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
- **sample_size:** N = 115 total across 3 experiments (after exclusions: N = 111). Exp 1: N = 24 (recruited 26; 12 female, age M = 23.75, SD = 3.22). Exp 2: N = 61 (recruited 64; Private N = 30, 20 female, age M = 22.27; Public N = 31, 22 female, age M = 22.58). Exp 3: N = 30 (recruited 32; 24 female, age M = 21.70, SD = 3.33). 4 additional subjects excluded post-model-fitting (MCMC non-convergence or implausible parameters).
- **population_category:** healthy adults
- **population_age_range:** M=23.75 (SD=3.22)
- **ecological_validity:** Task mimics real-world performance-feedback loops where people can perceive opportunity to improve, unlike prior work on unchangeable self-attributes. However, participants could not actually improve estimation performance (feedback was manipulated), and the cognitive estimation domain is novel/low-stakes rather than ecologically meaningful. Laboratory setting with university student sample.
- **eligibility_flag:** 
- **concerns:** (1) Feedback was entirely manipulated — participants believed they could improve but could not, which may confound perceived controllability with the negativity bias finding. (2) The task domain (cognitive estimation) is deliberately low-relevance; unclear if findings generalize to high-stakes self-relevant domains. (3) Sample is entirely university students, limiting generalizability. (4) Experiments 1 and 3 are not independent (combined for model comparison), so effective sample sizes for the Agent-LOOP are modest (N = 52 combined). (5) Social anxiety measured with SIAS in non-clinical range only.
- **limitations_reported:** The interpretation that self-improvement motives drove the negativity bias is speculative; participants could not actually improve performance; alternative factor of reduced task relevance compared to IQ or health feedback could reduce positivity bias; healthy sample with non-clinical social anxiety levels limits clinical generalizability; future studies needed to directly test impact of distinctive affective states like embarrassment and motives of self-enhancement or improvement on specific biases in self-related learning; do not know if the motivation to improve might have driven the individuals' learning behavior
- **limitations_categorized:** speculative mechanistic interpretation; limited ecological validity; task simplicity; limited generalizability (non-clinical sample); sample composition (university students); no manipulation of proposed mechanism (self-improvement motive)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** yes
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - social_param: MEDIUM confidence — alpha_PE-(S) is the key parameter but the paper frames the *difference* (Valence Bias Score) as the social parameter rather than alpha_PE-(S) alone - learning_mode source type: MEDIUM confidence — learning from manipulated feedback could be categorized as "world" (experimenter-generated) rather than "self"; classified as self because the paper frames it as learning from one's own performance outcomes - Initial value parameters: MEDIUM confidence — values not individually reported in text, only noted as estimated
- **cannot_find:** - Exact fitted values for initial value (IV) parameters across experiments - Prior distributions used for MCMC fitting (not specified in main text or supplement) - Exact formulas for priors on learning rate parameters
- **other_notes:** This paper is purely behavioural with no neuroimaging. The three experiments use the same LOOP paradigm with variations: Exp 1 = Agent-LOOP (self vs other, private), Exp 2 = Audience-LOOP (self only, private vs public), Exp 3 = Agent-LOOP (self vs other, public). Cumulative Bayesian analysis integrates evidence across all three. The supplement contains extended model comparison tables (18 models for Agent-LOOP, 9 for Audience-LOOP, including different initial value parameterizations) confirming the winning Valence Model. The paper's core finding -- that self-related learning shows a negativity bias opposite to the well-known positivity/optimism bias -- is novel and well-supported across experiments.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_source = social
- spec_target = social
- tax_domain_E_self_in_social_context
- tax_mod_active_interaction
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = self_esteem
- tax_rr_secondary_topic = self_belief_confidence
- tax_rr_topic_self_belief_confidence
- tax_rr_topic_self_esteem
- tax_topic_self_belief_confidence
- tax_topic_self_esteem
