# Hula et al. (2018)

- **study_id:** `a8ee4d53d01f352c4_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Hula, A., Vilares, I., Lohrenz, T., Dayan, P., & Montague, P. R. (2018). A model of risk and mental state shifts during social interaction. *PLoS Computational Biology*, *14*(2), e1005935. https://doi.org/10.1371/journal.pcbi.1005935
- **citation_short:** Hula et al. (2018)
- **doi:** 10.1371/journal.pcbi.1005935
- **publication_type:** peer-reviewed journal
- **year:** 2018.0
- **field_of_study:** Psychology
- **affiliations_raw:** CollegeLondon,London,UnitedKingdom,5DepartmentofPhysics,VirginiaPolytechnicInstituteandState; labilityStatement:TheURLunder strophicbreakdownscanariseamidstotherwiseefficientcooperation; CollegeLondon,London,UnitedKingdom,3HumanNeuroimagingLaboratory,VirginiaTechCarilion; Institute,Roanoke,Virginia,UnitedStatesofAmerica,4GatsbyComputationalUnit,University; InstituteofTechnology,Vienna,Austria,2WellcomeTrustCentreforNeuroimaging,University; ethatisabsentintheFehr-Schmidtmodelofother-regardingpreferencesthat; ethiscapacityisviatheso-calledinteractivePartiallyObservable; University,Blacksburg,Vir
- **code_url:** 

## Computational level
- **study_focus:** Trust learning; cooperation breakdown and repair in social exchange; computational phenotyping of borderline personality disorder in a trust game context.
- **study_focus_short:** Trust learning
- **learning_mode_description:** - Learning mode: Learning from partner's investment/return actions about partner's guilt (cooperativeness) and irritability over repeated interactions in a trust game.   - Learning from:     - Source type (social): other (dyadic partner — investor or trustee)     - Source content (social): action/policy (investment or return choices)   - Learning about:     - Target type (social): other (dyadic partner)     - Target content (social): state (mental state; guilt/inequality aversion and irritability)
- **task_description:** In a 10-round multi-round trust game, an investor receives 20 monetary units each round, chooses how much to invest with a trustee (amount tripled by experimenter), and the trustee decides how much to return; 93 healthy investors were paired with either 55 BPD-diagnosed trustees or 38 matched healthy control trustees.
- **task_paradigm:** Trust game
- **players:** Multi-agent (dyad), asymmetric (investor dominant; trustee subordinate)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Monetary endowments, investment/return amounts (numerical), no visual stimuli beyond game interface
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Full model (with risk aversion + irritation) predicts 43% of investor choices (chance = 20%) and 47% of trustee choices   - Investor average NLL improved from 12.96 (original model) to 9.68 (with risk aversion) to 8.4 (full model)   - Trustee average NLL improved from 11.37 to 9.5 (with risk aversion) to 7.6 (full model)   - Investor BIC improved from 27.3 to 21.68 (risk aversion) to 20.05 (full model)   - Trustee BIC improved from 24.1 to 21.4 (risk aversion) to 18.5 (full model)   - Risk aversion model vs. original: LRT p < 10^-46 (investor), p < 10^-11 (trustee)   - Full model vs. risk aversion model: LRT p = 0.006 (investor), p < 10^-12 (trustee)   - BPD trustees had significantly lower guilt than HC trustees (α^T: 0.32 vs. 0.49, p = 0.04 uncorrected)   - Higher proportion of guilt α^T = 0 in BPD (p = 0.02, χ² test, uncorrected)   - Irritation-ignorant setting (q^T(z) = 0) more common in BPD trustees (p = 0.03, χ² test, uncorrected)   - "Perilous" trustees (guilt-less or irritation-unaware): 60% in BPD vs. 29% in HC (p = 0.003, χ² test; survives Bonferroni correction for 7 comparisons, p < 0.05)   - Cross-game validation: risk aversion ω correlated with ultimatum game envy ρ (r = 0.16, p = 0.028 uncorrected) and inverse temperature β_u (r = -0.158, p = 0.036 uncorrected) in n = 178 sample
- **effect_size:** - Main Results:   - Full model (with risk aversion + irritation) predicts 43% of investor choices (chance = 20%) and 47% of trustee choices   - Investor average NLL improved from 12.96 (original model) to 9.68 (with risk aversion) to 8.4 (full model)   - Trustee average NLL improved from 11.37 to 9.5 (with risk aversion) to 7.6 (full model)   - Investor BIC improved from 27.3 to 21.68 (risk aversion) to 20.05 (full model)   - Trustee BIC improved from 24.1 to 21.4 (risk aversion) to 18.5 (full model)   - Risk aversion model vs. original: LRT p < 10^-46 (investor), p < 10^-11 (trustee)   - Full model vs. risk aversion model: LRT p = 0.006 (investor), p < 10^-12 (trustee)   - BPD trustees had significantly lower guilt than HC trustees (α^T: 0.32 vs. 0.49, p = 0.04 uncorrected)   - Higher proportion of guilt α^T = 0 in BPD (p = 0.02, χ² test, uncorrected)   - Irritation-ignorant setting (q^T(z) = 0) more common in BPD trustees (p = 0.03, χ² test, uncorrected)   - "Perilous" trustees (guilt-less or irritation-unaware): 60% in BPD vs. 29% in HC (p = 0.003, χ² test; survives Bonferroni correction for 7 comparisons, p < 0.05)   - Cross-game validation: risk aversion ω correlated with ultimatum game envy ρ (r = 0.16, p = 0.028 uncorrected) and inverse temperature β_u (r = -0.158, p = 0.036 uncorrected) in n = 178 sample
- **learning_from:** Other (dyadic partner); partner's investment/return actions in repeated trust game
- **learning_about:** Other (dyadic partner); partner's cooperativeness (guilt/inequality aversion) and irritability/emotional state  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** I-POMDP with Fehr-Schmidt utility, risk aversion, irritation, and irritation belief (7 params per subject: α, P, k, β, ω/b(ω), ζ, q(ζ))
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** [   {"name": "Original I-POMDP (α, P, k)", "family": "I-POMDP", "n_params": 3, "metric": "BIC, LRT"},   {"name": "I-POMDP + variable temperature (α, P, k, β)", "family": "I-POMDP", "n_params": 4, "metric": "BIC, LRT"},   {"name": "I-POMDP + risk aversion investor side (α, P, k, β, ω)", "family": "I-POMDP", "n_params": 5, "metric": "BIC, LRT"},   {"name": "I-POMDP + risk aversion belief trustee side (α, P, k, β, b(ω))", "family": "I-POMDP", "n_params": 5, "metric": "BIC, LRT"},   {"name": "I-POMDP + risk aversion + irritability only (α, P, k, β, ω, b(ω), ζ)", "family": "I-POMDP", "n_params": 6, "metric": "BIC, LRT"},   {"name": "Full I-POMDP (α, P, k, β, ω, b(ω), ζ, q(ζ))", "family": "I-POMDP", "n_params": 7, "metric": "BIC, LRT"} ]
- **model_mb_mf:** MB (model-based; agents build explicit models of partner's mental states and plan ahead using Bellman equations/dynamic programming)
- **model_params:** - α (guilt/inequality aversion) [S]: {0, 0.4, 1} — measure of tendency to reach fair outcome; intentional parameter inferred about partner via Bayesian updating - P (planning horizon): {1, 2, 3, 4} — number of steps planned ahead - k (Theory of Mind level) [S]: investors {0, 2, 4}, trustees {0, 1, 3} — depth of recursive mentalizing - β (inverse temperature): {1/4, 1/3, 1/2, 1} — certainty of choice preference - ω (risk aversion, investor) [S]: {0.4, 0.6, 0.8, 1.0, 1.2, 1.4, 1.6, 1.8} — value of money kept vs. potential money gained - b(ω) (risk aversion belief, trustee) [S]: {0.4, 0.6, 0.8, 1.0, 1.2, 1.4, 1.6, 1.8} — trustee's belief about investor's risk aversion - ζ (irritability) [S]: {0, 0.25, 0.5, 0.75, 1.0} — tendency to retaliate on worse-than-expected partner actions - q(ζ) (irritation belief/awareness) [S]: {0, 1, 2, 3, 4} — initial belief about partner's irritability
- **social_param:** α (guilt) — captures other-regarding preference/inequality aversion; k (Theory of Mind) — depth of recursive social reasoning; ζ (irritability) — propensity for anger/retaliation in response to partner defection; q(ζ) (irritation awareness) — belief about partner's irritability; ω/b(ω) (social risk aversion / belief about it) — valuation of kept vs. socially exchanged money
- **social_param_name:** α
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Likelihood Ratio Test (LRT; nested models compared via χ² statistic on summed NLL across subjects) and Bayesian Information Criterion (BIC) with small-sample correction
- **how_model_fit:** individual-level-fit (maximum likelihood estimation per subject, grid search over discrete parameter values)
- **data_type_fit_to:** choice behavior (investment and return decisions across 10 rounds)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A — no neuroimaging in this study
- **key_regions:** N/A — no neuroimaging in this study
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 186 (93 dyads: 93 healthy investors paired with 55 BPD trustees + 38 matched healthy control trustees). Data from King-Casas et al. (2008). Additional cross-validation sample: N = 178 healthy subjects (MRT + ultimatum game, supplement).
- **population_category:** mixed
- **population_age_range:** 
- **ecological_validity:** Lab-based economic game with discretized action spaces (5 options per player); real monetary incentives; interaction between real human dyads (not computer opponents); coarse grid approximation reduces ecological validity; 10-round horizon is short relative to real social relationships.
- **eligibility_flag:** 
- **concerns:** - 7 parameters fitted to only 10 data points per subject — potential overfitting concern (authors acknowledge this) - Discrete grid search over parameter space rather than continuous optimization - Reanalysis of existing dataset from King-Casas et al. (2008), not newly collected data - Group comparisons between BPD and HC trustees on model parameters are largely uncorrected for multiple comparisons (only the combined "perilous" group analysis survives Bonferroni) - Cross-validation with ultimatum game shows only weak correlations (r = 0.16 and r = -0.158) - Coarse action discretization (5 levels) may miss behavioral nuances - Supplement text extraction failed (scanned PDF); content read from PDF images directly
- **limitations_reported:** Psychiatric validity of model parameters has yet to be established; lack of additional clinical scales and personality measures for the populations; notion of perilousness derived post hoc on previously studied data; computational costs of planning limit exact calculation to planning horizon of 4; computational limitations force coarser representation of MRT than might be optimal in terms of possible subject actions and number of discrete parameter settings; investor awareness parameter not very reliably recovered; irritable subjects can be inferred as non-irritable if irritation is not excited during interaction.
- **limitations_categorized:** Limited clinical validity; lack of external validation measures; post hoc hypothesis derivation; computational constraints; parameter identifiability issues; limited parameter recovery; task simplicity (coarse discretization)
- **preregistered:** No
- **wc_rule1:** Partial
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 9.0
- **wc_total:** 9.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - effect_size: MEDIUM — effect sizes reported as NLL differences, BIC values, LRT p-values, proportions, and weak correlations; no standard Cohen's d or η² reported - ecological_validity: MEDIUM — inferred from task description - wc_guidelines rule 8: MEDIUM — validation is through simulate-and-compare rather than formal posterior predictive check
- **cannot_find:** - Mean fitted parameter values across the sample (distributions shown in Fig 3 but exact means not reported for all parameters except guilt: α^T BPD = 0.32, HC = 0.49) - Supplement text extraction failed; read directly from PDF images — no additional content beyond what was captured
- **other_notes:** - This is a reanalysis of behavioral data from King-Casas et al. (2008, Science) — flag for potential overlap with that paper if it appears in the corpus - The I-POMDP framework is relatively unusual in the social learning literature; it provides a sophisticated multi-agent planning model rather than a simple RL or Bayesian updating approach - The "perilous trustee" concept (guilt-less or irritation-unaware) is an interesting computational phenotype for BPD - Supplement text extraction failed (scanned PDF) but PDF was read as images successfully - Data and code publicly available on GitHub
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_bpd
- pop_healthy_adults
- rr_pop_bpd
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = structural
- spec_locus = target
- spec_source = social
- spec_target = social
- tax_domain_C_exchange_interdependence
- tax_mod_active_interaction
- tax_mod_mentalizing_inference
- tax_model_MB
- tax_model_bayesian
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_social_weight
- tax_rr_param_temperature
- tax_rr_primary_topic = trust
- tax_rr_secondary_topic = reciprocity
- tax_rr_topic_reciprocity
- tax_rr_topic_trust
- tax_topic_reciprocity
- tax_topic_trust
