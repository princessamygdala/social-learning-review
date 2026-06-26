# Diaconescu et al. (2020)

- **study_id:** `a7bae18ba1c06d93c_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Diaconescu, A. O., Stecy, M., Kasper, L., Burke, C. J., Nagy, Z., Mathys, C., & Tobler, P. N. (2020). Neural arbitration between social and individual learning systems. *eLife*, 9, e54051. https://doi.org/10.7554/eLife.54051
- **citation_short:** Diaconescu et al. (2020)
- **doi:** 10.7554/eLife.54051
- **publication_type:** peer-reviewed journal
- **year:** 2020.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** ETH Zurich, Zurich, Switzerland; 2Laboratory for Social and Neural; School, New Brunswick, United States; 6Institute for Biomedical; University of Toronto, Toronto, Canada; 5Rutgers Robert Wood; Centre for Neuroinformatics, Centre for Addiction and Mental; University of Basel, Department of Psychiatry (UPK), Basel,; Department of Economics, University of Zurich, Zurich,; Institute for Biomedical Engineering, University; Centre, Aarhus University, Aarhus, Denmark;; emails: andreea.diaconescu@utoronto.ca
- **code_url:** https://github.com/elifesciences-publi-

## Computational level
- **study_focus:** Learning from advice; arbitration between social and individual learning systems under volatility
- **study_focus_short:** Learning from advice
- **learning_mode_description:** - Learning mode: Learning from individually experienced card outcomes and social advice to predict lottery outcomes, arbitrating between sources based on relative precision   - Learning from:     - Source type (social): other (advisor)       - Source content (social): action/policy (advice recommendation about card color)     - Source type (non-social): self       - Source content (non-social): outcome (individually sampled card color outcomes)   - Learning about:     - Target type (social): other (advisor)       - Target content (social): state (mental state; advisor's fidelity/intentions and their volatility)     - Target type (non-social): world       - Target content (non-social): state (world state; card color reward probabilities and their volatility)
- **task_description:** Participants predicted the outcome of a binary card draw (blue or green) using recommendations from a gender-matched advisor (presented via video) and/or self-sampled card outcomes. They wagered 1–10 points on each prediction, with card color probabilities and advisor fidelity varying independently across stable and volatile phases in a 2x2 factorial design over 160 trials.
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), single advisor (pre-recorded video, gender-matched)
- **n_players:** single agent (1)
- **partner_type:** computer (algorithmic)
- **stimuli:** Pre-recorded advisor videos (2s each), binary card color outcomes (blue/green), wager scale (1–10 points), cumulative score feedback
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - Participants arbitrated between advice and individual card information based on relative precision; the arbitrated three-level HGF was the winning model (protected exceedance probability f_p = 0.999; Bayes Omnibus Risk = 4.26e-11)   - Social bias parameter z was significantly above zero (t(36) = 5.09, p = 1.07e-05), indicating participants relied more on advisor recommendations than own card sampling   - Learning parameters (κ, ω) did not differ between social and individual information sources and were highly correlated (r₁ = 0.55, p = 0.003 for κ; r₂ = 0.64, p = 0.001 for ω)   - Wager amount explained by belief uncertainty (t(37) = −10.37, p_bonf = 1.0e-11), arbitration (t(37) = 5.16, p_bonf = 5e-05), and estimated advisor volatility (t(37) = −7.41, p_bonf = 4.75e-08)   - Model-predicted wager correlated with actual wager across all conditions (r = 0.62–0.81)   - Advice helpfulness ratings explained by model parameters (R² = 32.2%, F = 2.46, p = 0.04), driven by κ_a (r(37) = 0.47, p = 0.0026)   - Arbitrating in favor of individual information: right DLPFC [36, 46, 30], left SMA/anterior cingulate sulcus [−2, −8, 52], midbrain/SN [−6, −18, −12]   - Arbitrating in favor of social information: right amygdala [18, −10, −16], vmPFC [−2, 46, −10], OFC [26, 34, −10], right anterior TPJ [56, −52, 24], right precuneus [6, −51, 32]   - Dopaminergic midbrain (SN) arbitrated in favor of individual information (ROI analysis, p < 0.05 FWE corrected)
- **effect_size:** - Cohen's f ≥ 0.4 for all parameter recovery comparisons - Wager–model correlations: r = 0.62 (advice stable), r = 0.63 (advice volatile), r = 0.81 (card stable), r = 0.80 (card volatile) - Advice helpfulness: R² = 32.2%; κ_a: r = 0.47 - Social bias z: t(36) = 5.09
- **learning_from:** Other (advisor's recommendations) and self (individually sampled card outcomes)
- **learning_about:** Other (advisor's fidelity/intentions and their volatility); world (card color reward probabilities and their volatility)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Arbitrated three-level HGF (2-branch hierarchical Gaussian filter with 3 levels per branch; 4 perceptual params: κ_a, κ_c, ω_a, ω_c; 1 social bias z; 1 decision noise β_ch; 6 wager response params b₁–b₆)
- **model_family:** HGF
- **model_class:** Belief updating
- **all_models_tested:** [   {"name": "Arbitrated 3-level HGF", "family": "Three-level HGF", "n_params": 12, "metric": "LME / BMS (protected exceedance probability)"},   {"name": "Advice-only 3-level HGF", "family": "Three-level HGF", "n_params": 11, "metric": "LME / BMS"},   {"name": "Card-only 3-level HGF", "family": "Three-level HGF", "n_params": 11, "metric": "LME / BMS"},   {"name": "Arbitrated Normative HGF", "family": "Normative HGF", "n_params": 10, "metric": "LME / BMS"},   {"name": "Advice-only Normative HGF", "family": "Normative HGF", "n_params": 9, "metric": "LME / BMS"},   {"name": "Card-only Normative HGF", "family": "Normative HGF", "n_params": 9, "metric": "LME / BMS"},   {"name": "Arbitrated 2-level HGF", "family": "Two-level HGF (no volatility)", "n_params": 10, "metric": "LME / BMS"},   {"name": "Advice-only 2-level HGF", "family": "Two-level HGF (no volatility)", "n_params": 9, "metric": "LME / BMS"},   {"name": "Card-only 2-level HGF", "family": "Two-level HGF (no volatility)", "n_params": 9, "metric": "LME / BMS"} ]
- **model_mb_mf:** Bayesian
- **model_params:** - κ_c (coupling, card): mean = 0.58, SD = 0.17 - κ_a (coupling, advice) [S]: mean = 0.56, SD = 0.28 - ω_c (meta-volatility, card): mean = 0.59, SD = 0.07 - ω_a (meta-volatility, advice) [S]: mean = 0.62, SD = 0.09 - z (social bias) [S]: mean = 1.03, SD = 1.24 - β_ch (decision noise / inverse temperature): mean = 2.25, SD = 0.92 - b₁ (belief uncertainty → wager): mean = −1.59, SD = 0.94 - b₂ (arbitration → wager): mean = 1.42, SD = 1.69 - b₃ (informational uncertainty advice → wager): mean = 0.23, SD = 1.37 - b₄ (informational uncertainty card → wager): mean = 0.63, SD = 1.24 - b₅ (volatility advice → wager): mean = −2.97, SD = 2.47 - b₆ (volatility card → wager): mean = −0.51, SD = 1.83
- **social_param:** z (social bias): log-space parameter reflecting degree of reliance on advisor recommendations independent of reliability; significantly positive (mean = 1.03), indicating participants preferentially weighted social over individual information. κ_a (coupling, advice) and ω_a (meta-volatility, advice) govern learning rate sensitivity to advisor volatility.
- **social_param_name:** κ_a
- **social_param_value:** 0.56
- **social_param_sd:** 0.28
- **social_param_range:** 
- **model_comparison_metric:** Log model evidence (LME) with random-effects Bayesian model selection (BMS); protected exceedance probability; Bayes Omnibus Risk
- **how_model_fit:** individual-level-fit (MAP estimation per participant using HGF toolbox v3.0 / TAPAS)
- **data_type_fit_to:** choice behavior and wager amount (wagered points as continuous confidence measure)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors derived from HGF computational trajectories) + univariate GLM (factorial analysis of task phases)
- **contrast:** - Undirected arbitration (F-test): ζ signal regardless of direction → vmPFC, OFC, frontopolar cortex, VLPFC, midbrain, amygdala, anterior insula, thalamus, cerebellum, occipital regions - Directed arbitration for individual information (ζ_c, positive t-contrast): → DLPFC, SMA/anterior cingulate sulcus, midbrain (SN) - Directed arbitration for social information (ζ_a, positive t-contrast): → amygdala, vmPFC, OFC, VLPFC, frontopolar cortex, anterior TPJ, STS, precuneus - Social weighting vs. non-social weighting: subgenual ACC > for social; bilateral cerebellum, occipital cortex, anterior cingulate sulcus > for non-social - Main effect of stability (stable > volatile): supramarginal gyrus, inferior occipital gyri, anterior insula, postcentral/precentral gyri - Information source × task phase interaction: midbrain, thalamus, OFC, VLPFC, SMA, occipital regions - Neuromodulatory ROI: SN (dopaminergic) activated by individual arbitration; PPT/LDT (cholinergic) by advice volatility PE
- **key_regions:** Arbitration for individual information in right DLPFC, left SMA/anterior cingulate sulcus, and dopaminergic midbrain (SN); arbitration for social information in right amygdala, vmPFC, OFC, VLPFC, anterior TPJ, STS, and precuneus; subgenual ACC for social weighting; cholinergic brainstem (PPT/LDT) for advice volatility PE.
- **key_regions_abbrev:** vmPFC, mPFC, dlPFC, OFC, ACC, sgACC, TPJ, STS, AI, amygdala, precuneus, midbrain
- **coordinates_peak:** Undirected arbitration (F-test): - Midbrain: −6, −18, −12 - Left thalamus: −12, −18, 8 - Left anterior insula: −44, 2, 0 - Right anterior insula: 48, 6, −2 - Right fusiform gyrus: 28, −78, −10 - Left fusiform gyrus: −28, −76, −10 - Right inferior occipital gyrus: 48, −68, −10 - Left inferior occipital gyrus: −42, −68, −4 - Right calcarine sulcus: 12, −86, 6 - Left superior temporal gyrus: −60, −30, −2 - Right superior temporal sulcus: 52, −18, −8 - Right amygdala: 18, −10, −16 - Right precuneus: 4, −52, 30 - Left dorsomedial PFC: −10, 44, 52 - Right superior medial PFC: 4, 56, 28 - Right VLPFC: 50, 36, 0 - Right frontopolar cortex: 4, 54, 30 - Right OFC: 26, 34, −10 - Left vmPFC: −2, 46, −10 - Right supramarginal gyrus: 54, −30, 50 - Right cerebellum: 18, −48, −18  Arbitration for individual card probability (ζ_c, positive): - Left midbrain: −6, −18, −10 - Left thalamus: −16, −18, 8 - Right thalamus: 22, −30, 4 - Left anterior insula: −44, 2, 0 - Right anterior insula: 36, 16, 8 - Left SMA/anterior cingulate sulcus: −2, −8, 52 - Right DLPFC: 36, 46, 30 - Right middle occipital gyrus: 12, −86, 6 - Left middle occipital gyrus: −32, −82, 16 - Right superior occipital gyrus: 28, −78, 30 - Left superior occipital gyrus: −26, −82, 32 - Right cerebellum: 18, −48, −18  Arbitration for social advice (ζ_a, positive): - Right precuneus: 6, −51, 32 - Right amygdala: 18, −10, −16 - Left anterior cingulate cortex: −2, 44, −10 - Right vmPFC: 8, 52, 14 - Right VLPFC: 50, 36, 0 - Right frontopolar cortex: 4, 62, 22 - Right OFC: 28, 26, −16 - Right middle frontal gyrus: 38, 14, 28 - Left superior temporal gyrus: −60, −30, −2 - Right superior temporal sulcus: 52, −18, −8 - Right anterior TPJ: 56, −52, 24 - Left cerebellum: −24, −84, −34
- **analysis_type:** both (whole-brain FWE cluster-level corrected + ROI analysis for neuromodulatory nuclei)  ---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 48 recruited (mean age 23.6 ± 1.4, 32 females); N = 38 entered final analysis (mean age 24.2 ± 1.3, 26 females) after excluding 10 (2 pilots, 1 head pain, 1 fell asleep, 6 stimulus malfunction)
- **population_category:** healthy adults
- **population_age_range:** M=23.6
- **ecological_validity:** Limited — pre-recorded advisor videos rather than live interaction; standardized advice sequence identical for all participants; binary lottery task is abstract and low in ecological validity. However, advisors were filmed during genuine interactive sessions and video clips were selected from trials with genuine helpful/misleading intent, improving social believability. Participants rated the advisor as intentional and helpful.
- **eligibility_flag:** 
- **concerns:** No non-social control condition was included, so it is unclear whether the "social" learning processes identified are truly specific to social information or reflect learning from any indirect information source. The advisor was pre-recorded video, not interactive. Relatively small final sample (N = 38) for the number of model parameters estimated.
- **limitations_reported:** One limitation of our study is that it did not include reciprocal social interactions, but rather used pre-recorded videos of human partners. ToM processes may be more prominent in interactive paradigms or interactions that involve higher levels of recursive thinking. By extension, our study may have limited generalizability to real-world social interactions"; "we did not include a non-social control task. Thus, it is unclear how 'social' the presently investigated form of learning about the advisor's fidelity and volatility actually is
- **limitations_categorized:** limited ecological validity; no non-social control condition; limited generalizability; non-interactive social partner
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 9
- **wc_total:** 9.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - n_params in all_models_tested: MEDIUM confidence — exact parameter counts not itemized per model; inferred from which parameters are free vs. fixed across model families - model_mb_mf: HIGH — classified as Bayesian (not RL) - ecological_validity: HIGH — limitations explicitly discussed by authors
- **cannot_find:** - Supplement not accessible (no supplement file found; figures supplements referenced in text are embedded figure supplements in eLife format, not a separate supplementary document) - Exact number of free parameters per model variant not explicitly tabulated (inferred from model descriptions)
- **other_notes:** Published in eLife (open access). The paper includes embedded figure supplements (e.g., Figure 2—figure supplement 1 for parameter recovery) that are part of the main article in eLife format rather than a separate supplement file. The HGF toolbox (TAPAS) is open source and code is available. This study builds on prior work by Diaconescu et al. (2014, 2017) using similar paradigms. The study is a single-study paper. Christoph Mathys is a co-author (developer of the HGF).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- rr_tax_mod_mentalizing_inference
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+context
- spec_neural = dedicated
- spec_source = partly
- spec_target = partly
- tax_domain_A_influence_transmission
- tax_mod_experiential
- tax_mod_instructed
- tax_mod_mentalizing_inference
- tax_model_HGF
- tax_model_bayesian
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_HGF
- tax_rr_model_family = HGF
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = advice_taking
- tax_rr_topic_advice_taking
- tax_rr_topic_social_info_use
- tax_topic_advice_taking
- tax_topic_precision_weighting
- tax_topic_social_info_use
