# Xiang et al. (2012)

- **study_id:** `a71954caf3dc912b6_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Xiang, T., Ray, D., Lohrenz, T., Dayan, P., & Montague, P. R. (2012). Computational phenotyping of two-person interactions reveals differential neural response to depth-of-thought. *PLoS Computational Biology*, *8*(12), e1002841. https://doi.org/10.1371/journal.pcbi.1002841
- **citation_short:** Xiang et al. (2012)
- **doi:** 10.1371/journal.pcbi.1002841
- **publication_type:** peer-reviewed journal
- **year:** 2012.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Department of Neuroscience, Baylor College of Medicine, Houston, Texas, United States of America, 2Computation and Neural Systems, California Institute of; depth-of-thoughtinthegame(low,medium,high),aparameterthatgovernstherichnessofthemodelstheybuildoftheir; depth-of-thought or cognitive is fully described by b[½0,1(cid:2), the ‘‘guilt’’ parameter; UniversityCollegeLondon,London,UnitedKingdom,5WellcomeTrustCentreforNeuroimaging,London,; ether or not the partner where x i isthemoneyobtainedbyplayeriandx j istheamount; depth-of-thought between two groups of healthy subjects: one playing; Instit
- **code_url:** 

## Computational level
- **study_focus:** Mentalizing learning / depth-of-thought in social exchange; computational theory-of-mind classification during strategic interaction
- **study_focus_short:** Mentalizing learning / depth-of-thought in social exchange
- **learning_mode_description:** - Learning mode: Learning from partner's reciprocation behavior about partner's type (inequality aversion) while recursively modeling the partner's model of oneself   - Learning from:     - Source type (social): other (trustee partner)     - Source content (social): action/policy (investment/return decisions)   - Learning about:     - Target type (social): other (trustee partner)     - Target content (social): state (mental state; type/guilt parameter, beliefs about oneself)  ---  ## (4) Computational Problem  How does a player infer and recursively update beliefs about a partner's type (inequality aversion) and the partner's model of oneself during iterated social exchange, to guide strategic investment decisions? (Prediction / evaluation — Bayesian belief updating about others' hidden types with recursive depth-of-thought)
- **task_description:** Pairs of subjects play a 10-round multi-round trust game. One player (investor) is endowed with $20 each round, chooses a fraction to send to a trustee (investment is tripled), and the trustee returns a fraction. Subjects are classified by depth-of-thought (levels 0, 1, 2) based on how deeply they model their partner's strategy.
- **task_paradigm:** Trust game
- **players:** Multi-agent (dyad), asymmetric (investor–trustee); 195 dyads total across 4 groups (Impersonal, Personal, BPD trustees, BPD-control trustees)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Monetary endowments, investment/return decisions; economic exchange game interface
- **method:** fMRI / behavioural
- **method_full:** fMRI + behavioural
- **main_result:** - Main Results:   - Computational ToM model fit behavior significantly better than chance (mean max log-likelihood = −11.92 ± 0.27 vs. chance = −16.1; one-sample test P = 1.51 × 10⁻³⁵)- RL model performed poorly; optimal learning rate was degenerate (no learning, random choices)- Level 1 and level 2 investors earned significantly more than level 0 investors (Tukey HSD, P < 10⁻⁶ and P < 10⁻⁵, respectively)- Level 0 investors: robust bilateral striatal activation for 1st order interpersonal PE (right caudate: t = 4.49; left caudate: t = 3.74; right putamen: t = 4.02; left putamen: t = 4.10; whole-brain FDR P < 0.05)- Level 0 > Level 1 caudate activation for 1st order PE (t = 4.04, FWE P < 0.05 SVC)- Level 2 > Level 0 right TPJ activation for 1st order PE (t = 4.70, whole-brain FDR P < 0.05)- Level 2 investors: bilateral putamen activation for 2nd order PE (right putamen: t = 3.79; left putamen: t = 3.11; whole-brain FDR P < 0.05)- Level 2 > Level 0 ventral striatal activation for 2nd order PE (t = 3.41, FWE P < 0.05 SVC)- BPD trustee group induced significantly different (lower) depth-of-thought distribution in investors vs. anonymous healthy trustees (Fisher's exact test, p = 1.68 × 10⁻⁶)
- **effect_size:** - Main Results:   - Computational ToM model fit behavior significantly better than chance (mean max log-likelihood = −11.92 ± 0.27 vs. chance = −16.1; one-sample test P = 1.51 × 10⁻³⁵)- RL model performed poorly; optimal learning rate was degenerate (no learning, random choices)- Level 1 and level 2 investors earned significantly more than level 0 investors (Tukey HSD, P < 10⁻⁶ and P < 10⁻⁵, respectively)- Level 0 investors: robust bilateral striatal activation for 1st order interpersonal PE (right caudate: t = 4.49; left caudate: t = 3.74; right putamen: t = 4.02; left putamen: t = 4.10; whole-brain FDR P < 0.05)- Level 0 > Level 1 caudate activation for 1st order PE (t = 4.04, FWE P < 0.05 SVC)- Level 2 > Level 0 right TPJ activation for 1st order PE (t = 4.70, whole-brain FDR P < 0.05)- Level 2 investors: bilateral putamen activation for 2nd order PE (right putamen: t = 3.79; left putamen: t = 3.11; whole-brain FDR P < 0.05)- Level 2 > Level 0 ventral striatal activation for 2nd order PE (t = 3.41, FWE P < 0.05 SVC)- BPD trustee group induced significantly different (lower) depth-of-thought distribution in investors vs. anonymous healthy trustees (Fisher's exact test, p = 1.68 × 10⁻⁶)
- **learning_from:** 
- **learning_about:** 
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Bayesian computational theory-of-mind (k-level) with inequality aversion utility (β_guilt; depth-of-thought k ∈ {0, 1, 2}; Bayesian belief updating over partner type)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** 
- **model_mb_mf:** MB (model-based — explicitly simulates partner's play and future course of game)
- **model_params:** - β_i (guilt/inequality aversion parameter) [S] — governs sensitivity to advantageous inequity; range [0, 1) - k_i (depth-of-thought level) [S] — discrete {0, 1, 2}; governs recursive depth of partner modeling - B⁰_i (prior beliefs over partner type) [S] — initial probability distribution over partner's guilt parameter - Softmax temperature (implicit in choice model — not explicitly named)  Mean fitted values: Not reported for individual parameters (classification frequencies: level 0 = 102/195; level 1 = 49/195; level 2 = 44/195 investors)
- **social_param:** k (depth-of-thought) — the depth of recursive mentalizing about the partner; β (guilt) — inequality aversion governing social preference
- **social_param_name:** β_i
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 0–1
- **model_comparison_metric:** Average negative log-likelihood comparison (Table S3 referenced but actual values only partially reported in main text: ToM model mean = −11.92 ± 0.27 vs. chance = −16.1; RL model degenerate with optimal learning rate yielding random behavior)  No formal BIC/AIC/BMS reported. Model comparison was based on log-likelihood and qualitative assessment (RL model was degenerate).  ---  ## (9) Neuroimaging
- **how_model_fit:** Individual-level fit (maximum likelihood estimation of parameters for each dyad)
- **data_type_fit_to:** Choice behavior (investment and return amounts across 10 rounds)  ---  ## (7) All Models Tested  1. **Bayesian computational theory-of-mind (k-level)** — Family: Bayesian belief updating / cognitive hierarchy; n_params: ~3 per player (β, k, prior); metric: log-likelihood 2. **Reinforcement learning with inequality aversion** — Family: RL (Rescorla-Wagner type); n_params: ~3 (k, β, learning rate ε); metric: log-likelihood (negative log-likelihood compared)  ---  ## (8) Model Comparison

## Implementation level
- **fmri_model_type:** Univariate GLM (model-based — prediction errors derived from computational model used to sort trials into quintiles, then contrast analysis on beta images)
- **contrast:** - 1st order interpersonal PE: high (>60th percentile) vs. low (≤40th percentile) quintiles at repayment revelation - 2nd order interpersonal PE: high vs. low quintiles at investment submission - Group contrasts (ANOVA): Level 0 vs. Level 1 vs. Level 2 on 1st and 2nd order PEs
- **key_regions:** 1st order interpersonal PE in bilateral caudate/putamen for level 0 investors; 2nd order interpersonal PE in bilateral putamen for level 2 investors; right TPJ for level 2 > level 0 on 1st order PE; ventral striatum for level 2 > level 0 on 2nd order PE.
- **key_regions_abbrev:** VS, caudate, putamen, striatum, TPJ
- **coordinates_peak:** - Right caudate: 8, 12, 0 (1st order PE, level 0; t = 4.49) - Left caudate: −12, 12, 4 (1st order PE, level 0; t = 3.74) - Right putamen: 24, 4, 0 (1st order PE, level 0; t = 4.02) - Left putamen: −24, 4, 4 (1st order PE, level 0; t = 4.10) - Caudate (level 0 > level 1): 4, 16, 0 (t = 4.04, FWE SVC) - Right TPJ (level 2 > level 0): 52, −48, 28 (t = 4.70) - Right putamen (2nd order PE, level 2): 24, 8, −4 (t = 3.79) - Left putamen (2nd order PE, level 2): −20, 8, −4 (t = 3.11) - Ventral striatum (level 2 > level 0, 2nd order PE): 12, 8, −12 (t = 3.41, FWE SVC)
- **analysis_type:** Both (whole-brain and ROI with SVC)
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 195 dyads (390 subjects total); ages 18–64 years. Four groups: Impersonal (48 pairs), Personal (54 pairs), BPD trustees (55 pairs), BPD-control (38 pairs). Neuroimaging analysis focused on investors only (n = 195 investors: level 0 = 102, level 1 = 49, level 2 = 44). Plus 38 lower-SES matched trustees.
- **population_category:** clinical
- **population_age_range:** 18–64
- **ecological_validity:** Moderate. Uses a real two-person economic exchange game with real monetary stakes and repeated interactions, which captures some naturalistic social dynamics. However, the trust game is a highly structured and simplified social interaction; communication is limited to monetary exchanges only. Mixed groups (some pairs met, some anonymous) adds some ecological range. BPD clinical group adds translational value.  ---  ## (13) Eligibility Flag  null (fully eligible — uses computational modeling, human behavioral data, learning occurs in a social context over multiple rounds)
- **eligibility_flag:** 
- **concerns:** - The RL comparison model is described only in supplementary material (Text S1) which is not accessible in this extraction; full model details and parameter recovery cannot be verified [MEDIUM] - No formal model comparison metric (BIC, AIC, BMS) — comparison is based on log-likelihood and qualitative assessment that RL is degenerate [HIGH] - No standardized effect sizes reported (only t-statistics and p-values for neural results) - Softmax/choice noise parameter not explicitly described in main text - Prior beliefs B⁰ specification not detailed in main text - The quintile-based contrast approach (sorting rounds by PE magnitude) is unconventional; not a standard parametric modulator approach - Mixed sample includes clinical (BPD) and control groups pooled for the main classification  ---  ## (15) Wilson-Collins Checklist  1. **Design a good experiment:** Yes — multi-round trust game engages strategic social learning 2. **Design good models:** Partial — two models compared (ToM vs. RL) but RL was degenerate; limited model space 3. **Simulate, simulate, simulate:** No — no evidence of simulation studies before fitting (model generates predictions but no explicit simulation-recovery reported) 4. **Fit the parameters:** Yes — MLE fitting reported for each dyad 5. **Check parameter recovery:** No — no parameter recovery analysis described 6. **Check model recovery:** No — no confusion matrix or model recovery analysis 7. **Fit real data and compare models:** Partial — compared ToM vs. RL on real data but RL was degenerate; comparison is not rigorous 8. **Validate the winning model:** Partial — behavioral trajectories by level correlate with model predictions (Fig 2B, 2C) but no formal posterior predictive check 9. **Analyze the winning model:** Yes — depth-of-thought classification used as grouping variable for neural and behavioral analyses 10. **Report results transparently:** Partial — code/data sharing not mentioned; supplementary materials referenced but limited detail in main text  ---  ## (16) Preregistered?  Not reported.  ---  ## Additional Fields
- **limitations_reported:** 
- **limitations_categorized:** 
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Partial
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.0
- **wc_total:** 5.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - `model_params`: Prior beliefs B⁰ and softmax temperature not detailed in main text (MEDIUM) - `all_models_tested`: RL model details only in Text S1, not accessible (MEDIUM) - `model_comparison_metric`: No formal information criterion used (HIGH — directly stated) - `effect_size`: No standardized effect sizes beyond t-values (MEDIUM)
- **cannot_find:** - Full RL model specification (in Text S1, not available) - Mean fitted parameter values for β (guilt) across groups - Softmax/choice noise parameter specification - Formal model comparison statistics (BIC/AIC)
- **other_notes:** - Published in PLoS Computational Biology (open access). Supplement (Text S1) is referenced for detailed model descriptions and RL comparison but not included in the extracted text file. The supporting information figures/tables (S1-S4) descriptions are included at the end of the main text but their actual content is image-based (TIF format). - The paper pools data from 4 previously published datasets (King-Casas et al., 2005, 2008; Tomlin et al., 2006; Bhatt et al., 2010) — potential overlap with other papers in the review corpus should be checked. - The recursive depth-of-thought model is closely related to cognitive hierarchy models from behavioral game theory (Camerer et al., 2004).
- **re_extract_flag:** false (full text accessed; supplement Text S1 not separately available but key results are in main text)

## Taxonomy / categorization (active codes only)
- pop_bpd
- pop_healthy_adults
- rr_pop_bpd
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_mentalizing_inference
- rr_tax_mod_multiplayer_live
- spec_context = social
- spec_depth = structural
- spec_locus = target
- spec_neural = dedicated
- tax_domain_B_inference_modelling_others
- tax_mod_active_interaction
- tax_mod_mentalizing_inference
- tax_mod_multiplayer_live
- tax_model_MB
- tax_model_bayesian
- tax_param_PE_signal
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_PE_signal
- tax_rr_param_social_weight
- tax_rr_primary_topic = strategic_reasoning
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_mentalizing
- tax_rr_topic_strategic_reasoning
- tax_topic_mentalizing
- tax_topic_strategic_reasoning
