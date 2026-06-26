# Diaconescu et al. (2014)

- **study_id:** `ad8c91c1b0277d469_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Diaconescu, A. O., Mathys, C., Weber, L. A. E., Daunizeau, J., Kasper, L., Lomakina, E. I., Fehr, E., & Stephan, K. E. (2014). Inferring on the intentions of others by hierarchical Bayesian learning. *PLoS Computational Biology*, *10*(9), e1003810. https://doi.org/10.1371/journal.pcbi.1003810
- **citation_short:** Diaconescu et al. (2014)
- **doi:** 10.1371/journal.pcbi.1003810
- **publication_type:** peer-reviewed journal
- **year:** 2014.0
- **field_of_study:** Psychology
- **affiliations_raw:** DepartmentofEconomics,UniversityofZurich,Zurich,Switzerland,3WellcomeTrustCentreforNeuroimaging,UniversityCollegeLondon,; InstituteforBiomedicalEngineering,UniversityofZurichandETHZurich,Zurich,Switzerland,2LaboratoryforSocialand; etheunderlyingmechanisms,weappliedcomputationalmodelingtobehavioraldatafromaneconomicgamein; depth of reasoning that leads to optimal inference; etheirpredictionsaboutthevalidityoftheiradvice; UniversityofMinnesota,UnitedStatesofAmerica; University CollegeLondon onComputational; DepartmentofComputerScience,ETHZurich,; emails: diaconescu@biomed.ee.ethz.ch
- **code_url:** 

## Computational level
- **study_focus:** Learning from advice / inferring on volatile intentions of others (trust learning, social inference under volatility)
- **study_focus_short:** Learning from advice / inferring on volatile intentions of others
- **learning_mode_description:** - Learning mode: Learning from an adviser's recommendations (which may be helpful or misleading) about the accuracy of advice and the volatility of the adviser's intentions   - Learning from:     - Source type (social): other (adviser)     - Source content (social): action/policy (adviser's recommendation — blue or green card)   - Learning about:     - Target type (social): other (adviser)     - Target content (social): state (mental state; intentions/trustworthiness — adviser's tendency to provide accurate vs. misleading advice and the volatility of those intentions)
- **task_description:** In a deception-free economic game, pairs of male participants were randomly assigned to "player" or "adviser" roles. The player predicted binary lottery outcomes using a pie chart showing outcome probabilities, while an adviser — who had more predictive information (80% accuracy) — issued recommendations; critically, the adviser's incentives to help or mislead varied over time due to differing payoff targets, requiring the player to track changes in the adviser's intentions.
- **task_paradigm:** Advice-taking task
- **players:** Multi-agent (dyad; player and adviser), asymmetric roles. 16 pairs total.
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Visual pie charts (6 blue:green probability levels), adviser's color card recommendations (blue/green), progress bar showing cumulative score, monetary reward targets (silver/gold ranges)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Three-level HGF with Volatility response model (M1) was the winning model (exceedance probability w = 0.99)   - Three-level HGF perceptual model family outperformed non-hierarchical models (w = 0.99)   - Integrated response model (social + non-social information) outperformed reduced models (w = 0.99)   - Volatility response model outperformed Decision Noise model (posterior probability p(r|y) = 0.94; w = 0.99)   - Parameters κ and v predicted IRI scores (R² = 0.50, F = 6.03, p < 0.02; log BF full vs. null = 15.16)   - Parameters ω and ζ predicted performance accuracy (R² = 0.40, F = 9.41, p < 0.01; log BF full vs. null = 17.59)   - Model estimates of advice reliability predicted explicit ratings of adviser helpfulness (t = 5.92, p < 0.0002)   - Players weighted non-social cue more than advice (ζ significantly < 0.5, p < 0.05)   - Players weighted advice more in social vs. control condition (ζ social = 0.39 vs. control = 0.28; t(15) = 2.44, p < 0.02)   - Players performed better in social vs. control task (73% ± 5% vs. 64% ± 2.6%; t(15) = 5.48, p < 0.00001)
- **effect_size:** - R² = 0.50 (κ, v predicting IRI) - R² = 0.40 (ω, ζ predicting performance accuracy) - log BF = 15.16 (κ, v → IRI, full vs. null) - log BF = 17.59 (ω, ζ → performance, full vs. null) - Cohen's d not reported; t-statistics reported (t = 5.92, t = 5.48, t = 2.44)
- **learning_from:** Other (adviser); adviser's trial-by-trial recommendations combined with non-social pie chart probabilities
- **learning_about:** Other (adviser); adviser's intention to help or mislead (advice accuracy and volatility of intentions)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Three-level HGF with Volatility response model (M1): hierarchical Gaussian filter with 3 levels (x₁ = advice accuracy [binary], x₂ = adviser helpfulness tendency, x₃ = log-volatility of adviser's intentions); response model integrates social and non-social information weighted by ζ, with decision noise varying as a function of estimated adviser volatility e^(−m₃). Parameters: κ, v, ω, initial beliefs m₂⁰, σ₂⁰, m₃⁰, σ₃⁰, ζ.
- **model_family:** HGF
- **model_class:** PE learning / Belief updating
- **all_models_tested:** [   {"name": "M1: HGF + Volatility + Integrated", "family": "Three-level HGF", "n_params": 8, "metric": "Random-effects BMS (exceedance probability)"},   {"name": "M2: HGF + Volatility + Advice only", "family": "Three-level HGF", "n_params": 7, "metric": "Random-effects BMS"},   {"name": "M3: HGF + Volatility + Cue only", "family": "Three-level HGF", "n_params": 4, "metric": "Random-effects BMS"},   {"name": "M4: HGF + Decision Noise + Integrated", "family": "Three-level HGF", "n_params": 8, "metric": "Random-effects BMS"},   {"name": "M5: HGF + Decision Noise + Advice only", "family": "Three-level HGF", "n_params": 7, "metric": "Random-effects BMS"},   {"name": "M6: HGF + Decision Noise + Cue only", "family": "Three-level HGF", "n_params": 4, "metric": "Random-effects BMS"},   {"name": "M7: No-Volatility HGF + Integrated", "family": "Reduced two-level HGF", "n_params": 6, "metric": "Random-effects BMS"},   {"name": "M8: No-Volatility HGF + Advice only", "family": "Reduced two-level HGF", "n_params": 5, "metric": "Random-effects BMS"},   {"name": "M9: No-Volatility HGF + Cue only", "family": "Reduced two-level HGF", "n_params": 2, "metric": "Random-effects BMS"},   {"name": "M10: RW + Integrated", "family": "Rescorla-Wagner", "n_params": 4, "metric": "Random-effects BMS"},   {"name": "M11: RW + Advice only", "family": "Rescorla-Wagner", "n_params": 3, "metric": "Random-effects BMS"},   {"name": "M12: RW + Cue only", "family": "Rescorla-Wagner", "n_params": 2, "metric": "Random-effects BMS"} ]
- **model_mb_mf:** Bayesian (not RL; hierarchical Bayesian belief updating)
- **model_params:** - κ: coupling parameter between x₂ and x₃ (mean = 0.31, SD = 0.29) [S] — determines how strongly inference on advice accuracy is coupled to volatility of adviser's intentions - v: tonic log-volatility at second level (mean = −5.92, SD = 2.93) — constant component of log-volatility of x₂ - ω: meta-volatility / step size of x₃ random walk (mean = 0.44, SD = 0.27) [S] — how quickly estimates of adviser's intention volatility evolve - m₂(k=0): initial belief about adviser helpfulness (mean = 0.48, SD = 0.53) - σ₂(k=0): initial uncertainty about adviser helpfulness (mean = 1.06, SD = 0.27) - m₃(k=0): initial belief about adviser volatility (mean = 0.42, SD = 0.61) - σ₃(k=0): initial uncertainty about adviser volatility (mean = 1.05, SD = 0.13) - ζ (f): weight of social information (advice) vs. non-social cue (mean = 0.39, SD = 0.12) [S] — integration of social vs. non-social sources - Note: Decision noise in the Volatility response model is determined dynamically by e^(−m₃), not by a fixed β parameter
- **social_param:** - κ [S]: coupling between inference on advice accuracy and volatility of adviser's intentions; stronger κ means adviser volatility more strongly shapes learning about advice reliability - ω [S]: meta-volatility of adviser's intentions; controls speed of updating beliefs about adviser intention stability - ζ (f) [S]: weight of social (advice) vs. non-social (cue) information in decision-making
- **social_param_name:** ζ
- **social_param_value:** 0.31
- **social_param_sd:** 0.29
- **social_param_range:** 
- **model_comparison_metric:** Random-effects Bayesian model selection (exceedance probability); family-level inference; log Bayes factors (individual and group level)
- **how_model_fit:** individual-level-fit (MAP estimation using quasi-Newton optimization; verified with Gaussian Process Optimization and MCMC)
- **data_type_fit_to:** choice behavior (trial-by-trial binary decisions: follow vs. go against advice)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study only; no neuroimaging)
- **key_regions:** N/A (behavioural study; authors note this is a precursor to future neuroimaging studies)
- **coordinates_peak:** N/A — no neuroimaging data
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 32 (16 pairs; 16 players and 16 advisers); all healthy male adults, age range 19–30, median age 22
- **population_category:** healthy adults
- **population_age_range:** 19–30
- **ecological_validity:** Deception-free interactive paradigm with real human adviser-player dyads (improvement over computer-generated advice used in Behrens et al., 2008). However, the game is a stylized economic game with binary choices, limited to dyadic interaction, and restricted to male participants only to avoid gender confounds.
- **eligibility_flag:** 
- **concerns:** All-male sample limits generalizability; relatively small sample (N = 16 players for model fitting); only players' learning was modeled (not advisers' recursive perspective-taking); no neuroimaging data in this paper; the 6 pie chart cue levels are relatively simple; no cross-validation reported for the winning model
- **limitations_reported:** The present models aimed to explain only the players' learning during the game, and not the advisers'; they neglected the recursive process of perspective-taking (the player's belief about the adviser's belief about the player's belief etc.), which occurs in many social situations; only men participated in this study to avoid potential gender-related confounds in the pairings of advisers and players; the modeling approach serves as a precursor for future neuroimaging studies
- **limitations_categorized:** limited recursive modeling; limited generalizability (gender); no neuroimaging; task simplicity
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Partial
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 9.5
- **wc_total:** 9.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM — parameter names in the text use varied notation (f vs. ζ, q vs. ω); mapped as faithfully as possible from Table 7 and equations - n_params for each model: MEDIUM — inferred from prior table (Table 2) showing which parameters are free vs. fixed; exact counts not explicitly stated per model - effect_size: MEDIUM — no standardized effect sizes (Cohen's d, η²) reported; R², t-statistics, log Bayes factors, and exceedance probabilities provided instead
- **cannot_find:** - Exact number of free parameters per model not explicitly listed in a single table - No MNI coordinates (behavioural study) - No standardized effect sizes (Cohen's d, η²) - Supplement figures (S1–S4) described as TIF files — content described in text but images not accessible in .txt format
- **other_notes:** This paper is a foundational study in the HGF/TAPAS framework applied to social learning. It serves as precursor to the Diaconescu et al. (2017) fMRI study. The control condition (blindfolded adviser sampling from card decks) provides a useful non-intentional comparison. The paper demonstrates that hierarchical Bayesian learning explains social inference better than simple reinforcement learning, and that volatility estimates drive both learning rates and decision noise. Code is freely available as part of TAPAS (http://www.translationalneuromodeling.org/tapas). Supplement not available as separate file; supporting information (Figures S1–S4, Video S1) described in paper text but TIF/MOV files not accessible.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_instructed
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = general
- spec_locus = source+target+context
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_B_inference_modelling_others
- tax_mod_active_interaction
- tax_mod_instructed
- tax_mod_mentalizing_inference
- tax_model_HGF
- tax_model_bayesian
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_HGF
- tax_rr_model_family = HGF
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = advice_taking
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_advice_taking
- tax_rr_topic_mentalizing
- tax_social_nonsocial_comparison
- tax_topic_advice_taking
- tax_topic_mentalizing
