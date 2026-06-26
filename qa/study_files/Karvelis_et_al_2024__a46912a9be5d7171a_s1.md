# Karvelis et al. (2024)

- **study_id:** `a46912a9be5d7171a_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Karvelis, P., Hauke, D. J., Wobmann, M., Andreou, C., Mackintosh, A., de Bock, R., Borgwardt, S., & Diaconescu, A. O. (2024). Test-retest reliability of behavioral and computational measures of advice taking under volatility. *PLoS ONE*, *19*(11), e0312255. https://doi.org/10.1371/journal.pone.0312255
- **citation_short:** Karvelis et al. (2024)
- **doi:** 10.1371/journal.pone.0312255
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Institutesof However,forthecomputationalmeasurestobesufficientlyinformativeattheindividual; DepartmentofPsychiatry(UPK),UniversityofBasel,Basel,Switzerland,5DepartmentofPsychiatryand; UniversityofToronto,Toronto,ON,Canada,7DepartmentofPsychology,UniversityofToronto,; DepartmentofPsychiatry,UniversityofToronto,Toronto,ON,Canada,3CentreforMedical; CentreforNeuroinformatics,CentreforAddictionandMentalHealth(CAMH),Toronto,ON,; ethequalityoffutureresearchandincreasetheprobabilityofclinicaltranslation; DepartmentofComputerScience,UniversityCollegeLondon,London,UnitedKingdom,; mpiricalevidenceindicat
- **code_url:** https://github.com/povilaskarvelis/compi_ioio_

## Computational level
- **study_focus:** Learning from advice / trust learning under volatility — specifically, how people infer the changing intentions (helpful vs. unhelpful) of an adviser and learn to trust or distrust their advice over time. The primary focus is on test-retest reliability of the computational assay measuring this process.
- **study_focus_short:** Learning from advice / trust learning under volatility
- **learning_mode_description:** - Learning mode: Learning from volatile social advice to infer an adviser's changing intentions (trustworthiness/fidelity)   - Learning from:     - Source type (social): other (adviser)       - Source content (social): action/policy (advice accuracy — whether adviser's recommendation matches outcome)     - Source type (non-social): world       - Source content (non-social): outcome (binary lottery outcome; pie chart cue indicating true probabilities)   - Learning about:     - Target type (social): other (adviser)       - Target content (social): state (mental state; intentions — helpfulness vs. unhelpfulness, fidelity)     - Target type (non-social): world       - Target content (non-social): state (volatility of adviser's intentions — environmental volatility)
- **task_description:** Participants completed a probabilistic learning task where on each trial they predicted the outcome of a binary lottery using a non-social cue (pie chart showing true winning probabilities) and a social cue (prerecorded video recommendation from a human adviser whose helpfulness changed over time). The task had a stable phase with consistent helpful advice and a volatile phase where the adviser's intentions changed rapidly across 153 trials.
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), single target (adviser via prerecorded video)
- **n_players:** single agent (1)
- **partner_type:** human (recorded)
- **stimuli:** Pie charts (non-social cue showing reward probabilities), prerecorded video of human adviser holding up colored cards, binary lottery outcomes
- **method:** fMRI / EEG / behavioural
- **method_full:** behavioural (note: data collected during fMRI and EEG sessions, but only behavioral data analyzed in this paper)
- **main_result:** - Main Results:   - Most computational parameter estimates had poor test-retest reliability (ICC < 0.5), except decision noise (ICC = 0.56, moderate)   - Behavioral measures also had largely poor reliability; accuracy ICC = 0.61, win-stay ICC = 0.52   - Parameter recovery was substantially higher than test-retest reliability for all parameters, indicating within-subject variability as a major source of low reliability   - Practice effects were moderate for prior fidelity expectation (d = 0.37) and advice weighting (d = 0.42), but contributed only ICC reduction of 0.02-0.03   - Mean-reverting HGF (model 2) was the winning model in both sessions (PEP ~0.7 session 1, ~1.0 session 2)   - Most poorly recovered parameter was $\kappa_2$ (ICC = 0.44); most recoverable was $\omega_2$ (ICC = 0.96)   - Face validity confirmed: model-derived fidelity estimates ($\hat{m}_2$) covaried with explicit reports of adviser helpfulness (p < 0.01 both sessions)
- **effect_size:** - ICC for accuracy = 0.61 [CI not specified in extracted text] - ICC for win-stay = 0.52 - ICC for decision noise $\nu$ = 0.56 - ICC for $\kappa_2$ = 0.04 (improved to 0.40 [0.09, 0.64] after removing influential data points) - Parameter recovery ICC for $\omega_2$ = 0.96 - Parameter recovery ICC for $\kappa_2$ = 0.44 - Practice effect Cohen's d for $\mu_2^{(0)}$ = 0.37 - Practice effect Cohen's d for z = 0.42 - BF01 = 5.6 for no change in accuracy across sessions
- **learning_from:** Other (adviser's advice accuracy/fidelity); world (pie chart cue, lottery outcomes). Source: other + world.
- **learning_about:** Other (adviser's intentions/trustworthiness/fidelity and their volatility). Target: other.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Mean-reverting 3-level HGF (model 2): 7 free parameters ($\mu_2^{(0)}$, $\mu_3^{(0)}$, $\kappa_2$, $\omega_2$, $m_3$, $z$, $\nu$); $\vartheta$ fixed = 0.5, $\phi_3$ fixed = 0.1
- **model_family:** HGF
- **model_class:** Belief updating
- **all_models_tested:** [   {"name": "Model 1: Standard 3-level HGF", "family": "Hierarchical Gaussian Filter", "n_params": 6, "metric": "Random-effects BMS (PEP)"},   {"name": "Model 1b: Standard HGF, Bayes Optimal (fixed perceptual params)", "family": "Hierarchical Gaussian Filter", "n_params": 2, "metric": "Random-effects BMS (PEP)"},   {"name": "Model 2: Mean-reverting 3-level HGF (WINNING)", "family": "Hierarchical Gaussian Filter", "n_params": 7, "metric": "Random-effects BMS (PEP)"},   {"name": "Model 2b: Mean-reverting HGF, Bayes Optimal (fixed perceptual params)", "family": "Hierarchical Gaussian Filter", "n_params": 2, "metric": "Random-effects BMS (PEP)"} ]
- **model_mb_mf:** Bayesian
- **model_params:** - $\mu_2^{(0)}$ [S]: Prior expectation about adviser's fidelity before task; prior mean = 0, variance = 1 - $\mu_3^{(0)}$ [S]: Prior expectation about adviser's volatility before task; prior mean = 1, variance = 1 - $\kappa_2$ [S]: Phasic learning rate / coupling strength between levels 2 and 3 (how volatility modulates learning about fidelity); prior mean = 0, variance = 1, upper bound = 1 - $\omega_2$ [S]: Tonic/baseline learning rate (evolution rate) at level 2, independent from level 3 estimates; prior mean = -2, variance = 4 - $m_3$ [S]: Volatility equilibrium point towards which beliefs about volatility drift; prior mean = 1, variance = 1 - $z$ [S]: Relative weighting of advice (social cue) compared to non-social cue (pie chart); prior mean = 0, variance = 1, upper bound = 1 - $\nu$: Decision noise independent of perceived volatility; prior mean = log(48), variance = 1 - $\vartheta$ (FIXED = 0.5): Meta-volatility at level 3 - $\phi_3$ (FIXED = 0.1): Drift rate at level 3
- **social_param:** - $z$: Relative weighting of social advice vs. non-social cue — captures how much participants rely on the adviser relative to objective probability information - $\mu_2^{(0)}$: Prior expectation about adviser's fidelity — captures initial trust/beliefs about adviser helpfulness - $\kappa_2$: Phasic learning rate coupling volatility to fidelity learning — how perceived volatility of adviser's intentions modulates learning about their current helpfulness
- **social_param_name:** $\mu_2^{
- **social_param_value:** 0
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Random-effects Bayesian model selection using protected exceedance probabilities (PEP), implemented via VBA toolbox. Free energy approximation of Bayesian model evidence.
- **how_model_fit:** individual-level-fit (quasi-Newton optimization to find parameter values with highest posterior probability)
- **data_type_fit_to:** choice behavior (binary choice: go with or against advice)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (behavioral data only analyzed; fMRI/EEG data were collected but not analyzed in this paper)
- **contrast:** 
- **key_regions:** N/A (no neuroimaging analysis reported)
- **coordinates_peak:** N/A — no neuroimaging analysis in this paper
- **analysis_type:** N/A (no neuroimaging)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** N = 39 healthy participants (20 female, 19 male; mean age = 28.85, SD = 4.03); 4 additional participants excluded for completing only one session (from initial N = 43)
- **population_category:** healthy adults
- **population_age_range:** M=28.85
- **ecological_validity:** Limited. Adviser was a prerecorded video (not live interaction). Binary lottery task with pie chart cues is abstract. The social interaction is unidirectional (participant receives advice but does not interact back). However, the changing intentions of the adviser add ecological complexity relative to static social cues.
- **eligibility_flag:** The primary focus of this paper is on psychometric properties (test-retest reliability) of the computational assay rather than on social learning mechanisms per se. The paper does use computational modeling with human behavioral data in a social learning context (learning about an adviser's intentions over time), so it meets inclusion criteria. However, the study is essentially a reliability/methods paper, not a substantive investigation of social learning. FLAG: primary focus is psychometric evaluation rather than social learning mechanisms.
- **concerns:** - The paper's primary aim is test-retest reliability assessment, not investigating social learning mechanisms — results are about measurement properties rather than social learning findings - Small sample (N = 39) with wide confidence intervals around ICC estimates - Mean fitted parameter values are not reported in the paper (only priors are given in Table 1) - No individual-level fitted parameter means provided - The task uses a prerecorded adviser video, not a real social interaction
- **limitations_reported:** Sample size was relatively small (N = 39), resulting in wide confidence intervals around ICC values; test and retest sessions were done during EEG and fMRI scanning which may have contributed to error variance despite no fixed effects found; parameter recovery analysis only indicates intrinsic measurement error while actual measurement error is likely higher due to model-reality mismatch; practice effects analysis accounts only for fixed effects and not idiosyncratic practice effects; social nature of task may have led to higher-level strategies during first session based on prior expectations of deception; state-like fluctuation data (mood, motivation) were not collected; ability to explore nuanced questions was limited by experimental design
- **limitations_categorized:** sample size; measurement context confound (EEG/fMRI environments); model misspecification; limited ecological validity; practice effects; demand characteristics / deception concerns; unmeasured state-like confounds; limited experimental design
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 9.5
- **wc_total:** 9.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `winning_model`: MEDIUM confidence — mean fitted parameter values not reported, only priors given - `eligibility_flag`: MEDIUM confidence — paper meets technical inclusion criteria but primary focus is psychometric methodology - `effect_size`: HIGH confidence — ICCs and Cohen's d values directly reported - `model_params`: MEDIUM confidence — all parameters listed with priors but no mean fitted values available
- **cannot_find:** - Mean fitted parameter values for the winning model (not reported in main text or supplement) - Exact ICC confidence intervals for all behavioral measures (some shown in figures but not all extractable from text) - Exact protected exceedance probability for session 1 (~0.7 reported with approximation symbol)
- **other_notes:** This paper is primarily a psychometric/methods contribution examining whether the HGF-based advice-taking assay has adequate test-retest reliability for individual-differences research and clinical translation. The core finding is negative — most measures have poor reliability. The paper is part of a larger study (Hauke et al., 2024) investigating first-episode psychosis and clinical high-risk, but only healthy controls are analyzed here. Data and code are openly shared. The supplement confirms model recovery results and provides additional analyses (collinearity tests, EEG vs fMRI environment effects, comparison with prior studies' reliability, and analysis with matched trial numbers to Hauke et al. 2024).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = partly
- spec_depth = general
- spec_locus = source+target+context
- spec_source = partly
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_G_uncertainty_volatility
- tax_mod_experiential
- tax_mod_instructed
- tax_model_HGF
- tax_model_bayesian
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_HGF
- tax_rr_model_family = HGF
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = advice_taking
- tax_rr_secondary_topic = social_uncertainty
- tax_rr_topic_advice_taking
- tax_rr_topic_social_uncertainty
- tax_social_nonsocial_comparison
- tax_topic_advice_taking
- tax_topic_social_uncertainty
