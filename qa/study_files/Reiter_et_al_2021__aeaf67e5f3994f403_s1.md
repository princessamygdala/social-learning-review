# Reiter et al. (2021)

- **study_id:** `aeaf67e5f3994f403_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Reiter, A. M. F., Diaconescu, A. O., Eppinger, B., & Li, S.-C. (2021). Human aging alters social inference about others' changing intentions. *Neurobiology of Aging*, 103, 98–108. https://doi.org/10.1016/j.neurobiolaging.2021.01.034
- **citation_short:** Reiter et al. (2021)
- **doi:** 10.1016/j.neurobiolaging.2021.01.034
- **publication_type:** peer-reviewed journal---
- **year:** 2021.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** Department of Child and Adolescent Psychiatry, Psychosomatics and Psychotherapy, Center of Mental Health, University of Würzburg, Würzburg, Germany; Centre for Neuroinformatics, Centre for Addiction and Mental Health (CAMH), University of Toronto, Canada; Department of Neurology, Max-Planck-Institute for Human Cognitive and Brain Sciences, Leipzig, Germany; UCL Centre for Computational Psychiatry and Ageing Research, University College London, London, UK; Centre for Tactile Internet With Human-in-the-Loop, Technische Universität Dresden, Germany; Faculty of Psychology, Technische Universität D
- **code_url:** 

## Computational level
- **study_focus:** Learning from advice; social inference about others' changing intentions; trust learning; learning about adviser fidelity and volatility across the lifespan
- **study_focus_short:** Learning from advice · social inference about others' changing intentions
- **learning_mode_description:** - Learning mode: Learning from an adviser's accuracy/inaccuracy about the adviser's time-varying fidelity and volatility of intentions   - Learning from:     - Source type (social): other (adviser)       - Not joint     - Source content (social): action/policy (advice accuracy — whether the adviser's recommendation matched the outcome)       - Not joint   - Learning about:     - Target type (social): other (adviser)       - Not joint     - Target content (social): state (mental state; intentions — adviser's fidelity and volatility of intentions)       - Not joint
- **task_description:** In a binary lottery game (120 trials), participants decided whether to bet on blue or green. Before choosing, they saw a pie chart showing true winning probabilities and a video of an adviser recommending a colour; advice validity shifted across stable-volatile-stable phases, and participants had to track the adviser's changing fidelity.
- **task_paradigm:** Advice-taking task
- **players:** Single agent (participant), dyadic (pre-recorded adviser; within-subject: younger and older adviser)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Pie charts (colour probabilities), pre-recorded video of adviser holding up a coloured card, binary feedback (correct/incorrect colour)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Significant main effect of participants' age group on HGF parameters (MANOVA: F = 6.40, p < 0.001)   - OA had lower a priori fidelity beliefs (μ₂₀) than YA (F = 23.83, p < 0.001)   - OA had higher a priori volatility beliefs (μ₃₀) than YA (F = 6.90, p = 0.01)   - OA had lower meta-volatility parameter ϑ than YA (F = 6.69, p = 0.012)   - OA showed higher precision (π₃) in volatility beliefs than YA (χ² = 5.31, p = 0.021)   - OA had higher trial-by-trial learning rate α₂ than YA (χ² = 3.98, p = 0.046)   - YA assigned higher volatility to OA advisers than to YA advisers (χ² = 2.24, p = 0.03)   - YA assigned higher fidelity to OA advisers in the first stable phase (z ratio = 3.00, p = 0.003)   - Significant interaction of participants' age group × phase on advice-following (χ² = 12.60, p = 0.002)
- **effect_size:** Effect sizes reported as F-statistics and χ² from MANOVA and mixed models; no Cohen's d, r², or η² reported. [MEDIUM — effect sizes are test statistics only, not standardised effect sizes]
- **learning_from:** Other (adviser); adviser's accuracy/inaccuracy of advice (social)
- **learning_about:** Other (adviser); adviser's fidelity (probability of accurate advice) and volatility of intentions (social)---  ## ALGORITHMIC LEVEL
- **outcome_modality:** cognitive_only

## Algorithmic level
- **winning_model:** 3-level HGF with volatility-influenced decision noise and social weighing parameter (5 free params: κ, ω, ϑ, ζ, β)
- **model_family:** HGF
- **model_class:** PE learning / Belief updating
- **all_models_tested:** - [{"name": "3-level HGF + volatility decision noise + integrated (advice+cue)", "family": "HGF", "n_params": 5, "metric": "BMS (exceedance probability)"}, - {"name": "3-level HGF + volatility decision noise + advice only", "family": "HGF", "n_params": 4, "metric": "BMS"}, - {"name": "3-level HGF + volatility decision noise + cue only", "family": "HGF", "n_params": 4, "metric": "BMS"}, - {"name": "3-level HGF + fixed decision noise + integrated", "family": "HGF", "n_params": 5, "metric": "BMS"}, - {"name": "3-level HGF + fixed decision noise + advice only", "family": "HGF", "n_params": 4, "metric": "BMS"}, - {"name": "3-level HGF + fixed decision noise + cue only", "family": "HGF", "n_params": 4, "metric": "BMS"}, - {"name": "2-level HGF + integrated", "family": "HGF (reduced)", "n_params": 3, "metric": "BMS"}, - {"name": "2-level HGF + advice only", "family": "HGF (reduced)", "n_params": 2, "metric": "BMS"}, - {"name": "2-level HGF + cue only", "family": "HGF (reduced)", "n_params": 2, "metric": "BMS"}, - {"name": "RW + integrated", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BMS"}, - {"name": "RW + advice only", "family": "Rescorla-Wagner", "n_params": 1, "metric": "BMS"}, - {"name": "RW + cue only", "family": "Rescorla-Wagner", "n_params": 1, "metric": "BMS"}]  (12 models total)
- **model_mb_mf:** Bayesian
- **model_params:** - κ (kappa): coupling between 2nd and 3rd level — how much volatility influences fidelity updating. Prior mean = 0, variance = 1. [No mean fitted value reported per group] - ω (omega): tonic log-volatility on second level — degree of fidelity belief updating independent of volatility. Prior mean = −2, variance = 1. [No mean fitted value reported per group] - ϑ (theta) [S]: meta-volatility — speed of volatility updating (governs 3rd level updating). Prior mean = 0, variance = 1. OA had significantly lower values than YA (F = 6.69, p = 0.012). - ζ (zeta) [S]: social weighing parameter — weight of social (advice) vs. non-social (pie chart) information. Prior mean = 0, variance = 1. - β (beta): inverse decision temperature — choice stochasticity; varies as function of estimated volatility in winning model. Prior mean = 48, variance = 1. - μ₂₀: initial fidelity belief (prior on 2nd level). Prior mean = 0, variance = 1. OA significantly lower than YA (F = 23.83, p < 0.001). - μ₃₀: initial volatility belief (prior on 3rd level). Prior mean = 1, variance = 1. OA significantly higher than YA (F = 6.90, p = 0.01). Note: μ₂₀, σ₂₀, μ₃₀, σ₃₀ are initial state values estimated per participant but listed separately from the 5 "free parameters" in Table 1. The paper reports MANOVA on "all seven free parameters." Mean fitted values per group are not numerically reported (shown in Fig. 3 cat-eye plots only).
- **social_param:** ζ (zeta) — weighing parameter for social vs. non-social information; ϑ (theta) — meta-volatility of the adviser's intentions (governs how quickly beliefs about the adviser's volatility are updated; showed significant age group differences)
- **social_param_name:** ϑ
- **social_param_value:** 0
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Random-effects Bayesian Model Selection (BMS) using negative variational free energy as approximation of log model evidence; exceedance probability (XP) and protected exceedance probability (PXP); family-level BMS
- **how_model_fit:** individual-level-fit (maximum a posteriori estimates via variational Bayesian inversion for each participant)
- **data_type_fit_to:** choice behavior (binary decisions: follow advice or not)---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study)
- **key_regions:** N/A (behavioural study; discussion references prior work linking 2nd-level PE to dopaminergic midbrain and 3rd-level PE to cholinergic basal forebrain, but no neural data collected in this study)
- **coordinates_peak:** N/A — no neuroimaging data collected
- **analysis_type:** N/A---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 67 (34 younger adults, age range 18–30, mean = 24.35, SD = 3.11, 21 female; 33 older adults, age range 65–80, mean = 71.97, SD = 3.95, 20 female). Original N = 82; exclusions for dementia screening (4), psychiatric conditions (3), neurological diagnosis (2), colour discrimination problems (2), technical errors (5), implausible model trajectories (3).
- **population_category:** mixed
- **population_age_range:** 18–30
- **ecological_validity:** Limited — pre-recorded video advisers rather than live social interaction; binary lottery game is abstract and does not capture real-world advice-taking complexity. The authors acknowledge the videos may have reduced the social aspect. Artificiality ratings showed no age-group difference (OA mean = 6.17, YA mean = 6.05 on 0–15.5 scale).
- **eligibility_flag:** 
- **concerns:** - Effect sizes are reported only as F-statistics and χ² values, not standardised effect sizes (d, η², etc.) - Mean fitted parameter values per group are displayed only in figure (cat-eye plots) and not numerically reported in text or tables - Pre-recorded video advisers rather than live interaction; ecological validity limited - Adviser input was pre-determined (not from actual interaction), limiting true social dynamics - No non-social control condition in this study (referenced from prior work by Diaconescu et al., 2014)
- **limitations_reported:** The videos used in the present study might have reduced the social aspect of the task and thus the ecological validity"; "Future studies could include a direct non-social comparison task to investigate the specificity of the social effects"; age-related changes in neuromodulation (dopaminergic/cholinergic) are discussed but not measured — "Future pharmacoimaging studies are needed to investigate the relationship between aging-related changes in neuromodulation and changes in dynamic social inference learning"
- **limitations_categorized:** limited ecological validity; no non-social control condition; no neural data; correlational (no causal neuromodulatory manipulation); task simplicity
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - effect_size [MEDIUM]: Only F and χ² statistics reported; no standardised effect sizes (d, η², etc.) - model_params fitted values [MEDIUM]: Mean MAP estimates per group not numerically reported; shown only in Fig. 3 cat-eye plots - wc_guidelines rule 3 [MEDIUM]: Parameter recovery was done but no explicit pre-data design simulation described - wc_guidelines rule 8 [MEDIUM]: Simulated-vs-empirical comparison shown in supplement but no formal posterior predictive check
- **cannot_find:** - Exact mean fitted parameter values per age group (displayed in figures only) - Standardised effect sizes - Data sharing statement
- **other_notes:** - This study builds directly on Diaconescu et al. (2014, 2017) using the same advice-taking paradigm and HGF framework, extended to an aging sample - Within-subject manipulation of adviser age (younger vs. older) is a novel feature - The paper discusses implications for stereotype research ("fickle but dear" older adults) - Text extraction from PDF was partially garbled (Tables 1 and 2 region, some results text corrupted), but all key information was recoverable from intact portions and the supplement
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- pop_older_adults
- rr_pop_healthy_adults
- rr_pop_older_adults
- rr_tax_mod_instructed
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = general
- spec_locus = source+target+context
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_B_inference_modelling_others
- tax_mod_instructed
- tax_mod_mentalizing_inference
- tax_model_HGF
- tax_model_bayesian
- tax_param_social_weight
- tax_popclass_developmental
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
