# Diaconescu et al. (2017)

- **study_id:** `a1b6b5214ee0f278c_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Diaconescu, A. O., Mathys, C., Weber, L. A. E., Kasper, L., Mauer, J., & Stephan, K. E. (2017). Hierarchical prediction errors in midbrain and septum during social learning. *Social Cognitive and Affective Neuroscience, 12*(4), 618–634. https://doi.org/10.1093/scan/nsw171
- **citation_short:** Diaconescu et al. (2017)
- **doi:** 10.1093/scan/nsw171
- **publication_type:** peer-reviewed journal
- **year:** 2017.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** mitsnon-commercialre-use,distribution,andreproductioninanymedium,providedtheoriginalworkisproperlycited; College,CornellUniversity,NewYork,NY,USA,and6WellcomeTrustCentreforNeuroimaging,University; InstituteforMetabolismResearch,Cologne,Germany,5DepartmentofPharmacology,WeillMedical; UniversityofZu¨richandETHZu¨rich,Wilfriedstrasse6CH-8023,Zu¨rich,Switzerland; LaboratoryforSocialandNeuralSystemsResearch,UniversityofZurich,Zurich,; UCLCentreforComputationalPsychiatryandAgeingResearch,London,UK,4Max; InstituteforBiomedicalEngineering,UniversityofZurich&ETHZurich,; mited pendently replicated using
- **code_url:** 

## Computational level
- **study_focus:** Social learning from advice; learning about an adviser's changing trustworthiness and intentions under volatility
- **study_focus_short:** Social learning from advice
- **learning_mode_description:** - Learning mode: Learning from an adviser's accuracy of advice about the trustworthiness and volatility of the adviser's intentions   - Learning from:     - Source type (social): other (adviser)     - Source content (social): action/policy (advice accuracy/validity)   - Learning about:     - Target type (social): other (adviser)     - Target content (social): state (mental state; trustworthiness/fidelity and volatility of intentions)
- **task_description:** Participants predicted the outcome of a binary lottery using information from a pie chart (non-social cue) and video-recorded advice from a pre-recorded adviser whose motivation to help or mislead changed over time. Participants had to learn about the adviser's changing intentions to decide whether to follow the advice.
- **task_paradigm:** Advice-taking task
- **players:** Single agent (participant), dyadic (pre-recorded adviser with changing intentions); N=82 total across two studies (N=35 study 1, N=47 study 2)
- **n_players:** network (5+)
- **partner_type:** human (live)
- **stimuli:** Pie charts (binary lottery probabilities), pre-recorded video clips of adviser giving advice, binary feedback (correct/incorrect prediction)
- **method:** fMRI
- **method_full:** fMRI (two separate studies), genetics (COMT and TH SNP genotyping)
- **main_result:** - Three-level HGF with integrated response model (M1) won model comparison in both studies (protected exceedance probability > 0.92 in both studies) - Model parameters jointly predicted task performance (R² = 28.36%, F = 4.09, P < 0.018 study 1; R² = 39%, F = 2.53, P < 0.02 study 2) - Social weighting parameter ζ independently predicted performance (R² = 17.67%, F = 7.08, P < 0.01 study 1; R² = 15%, F = 7.72, P < 0.01 study 2) - Low-level precision-weighted PEs (ε₂) about advice validity activated dopaminergic midbrain (VTA/SN), ACC, bilateral insula, dmPFC, dlPFC, TPJ (replicated across both studies) - High-level precision-weighted PEs (ε₃) about adviser volatility activated cholinergic septum and dorsal middle cingulate/dACC (replicated across both studies) - COMT Met/Met carriers showed enhanced low-level PE representation in ventral striatum compared to Val/Val carriers
- **effect_size:** - Model performance prediction study 1: R² = 0.28, F = 4.09 - Model performance prediction study 2: R² = 0.39, F = 2.53 - Social weight (ζ) on performance study 1: R² = 0.18, F = 7.08 - Social weight (ζ) on performance study 2: R² = 0.15, F = 7.72 - VTA/SN ε₂ study 1: t = 2.91 (ROI); study 2: t = 5.84 (whole-brain) - Septum ε₃ study 1: t = 4.11 (ROI); study 2: t = 3.43 (ROI) - COMT effect on ε₂ in dlPFC study 1: t(34) = 5.82 - Note: Most neural effects reported as t-scores with FWE correction; no Cohen's d or standardized effect sizes reported for neural contrasts
- **learning_from:** Other (adviser); advice accuracy/validity signals
- **learning_about:** Other (adviser); trustworthiness/fidelity and volatility of intentions  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** cognitive_only

## Algorithmic level
- **winning_model:** Three-level HGF with integrated response model (M1): κ coupling, ω tonic log-volatility, ϑ meta-volatility, ζ social weighting parameter, sigmoid response function with volatility-dependent decision noise
- **model_family:** HGF
- **model_class:** PE learning / Belief updating
- **all_models_tested:** [   {"name": "M1: HGF + Volatility + Integrated", "family": "HGF (3-level)", "n_params": 4, "metric": "BMS protected exceedance probability"},   {"name": "M2: HGF + Volatility + Advice only", "family": "HGF (3-level)", "n_params": 3, "metric": "BMS protected exceedance probability"},   {"name": "M3: HGF + Volatility + Cue only", "family": "HGF (3-level)", "n_params": 3, "metric": "BMS protected exceedance probability"},   {"name": "M4: HGF + Decision noise + Integrated", "family": "HGF (3-level)", "n_params": 4, "metric": "BMS protected exceedance probability"},   {"name": "M5: HGF + Decision noise + Advice only", "family": "HGF (3-level)", "n_params": 3, "metric": "BMS protected exceedance probability"},   {"name": "M6: HGF + Decision noise + Cue only", "family": "HGF (3-level)", "n_params": 3, "metric": "BMS protected exceedance probability"},   {"name": "M7: No-volatility HGF + Volatility resp + Integrated", "family": "HGF (2-level, no volatility)", "n_params": 3, "metric": "BMS protected exceedance probability"},   {"name": "M8: No-volatility HGF + Volatility resp + Advice only", "family": "HGF (2-level, no volatility)", "n_params": 2, "metric": "BMS protected exceedance probability"},   {"name": "M9: No-volatility HGF + Volatility resp + Cue only", "family": "HGF (2-level, no volatility)", "n_params": 2, "metric": "BMS protected exceedance probability"},   {"name": "M10: RW + Decision noise + Integrated", "family": "Rescorla-Wagner", "n_params": 3, "metric": "BMS protected exceedance probability"},   {"name": "M11: RW + Decision noise + Advice only", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BMS protected exceedance probability"},   {"name": "M12: RW + Decision noise + Cue only", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BMS protected exceedance probability"} ]
- **model_mb_mf:** Bayesian
- **model_params:** - κ (kappa): coupling between levels 2 and 3; mean = 0.41 (study 1), 0.52 (study 2) - ω (omega): tonic log-volatility of adviser fidelity; mean = -1.47 (study 1), -2.80 (study 2) - ϑ (theta): meta-volatility, evolution rate of x₃; mean = 0.38 (study 1), 0.43 (study 2) - ζ (zeta) [S]: social weighting parameter, balances social advice vs. non-social cue; mean = 0.40 (study 1), 0.45 (study 2)
- **social_param:** ζ (zeta) — weight assigned to social information (advice) relative to non-social cue (pie chart) when integrating information sources for decision-making. Higher ζ = greater reliance on social advice.
- **social_param_name:** ζ
- **social_param_value:** 0.40
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Random effects Bayesian model selection (BMS) with protected exceedance probabilities; family-level inference
- **how_model_fit:** individual-level-fit (MAP estimation using HGF toolbox v3.0, TAPAS)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors from HGF computational trajectories)
- **contrast:** - Negative ε₂ (low-level signed precision-weighted PE about advice validity): trials when adviser more misleading than predicted → VTA/SN, ACC, bilateral insula, dmPFC, dlPFC, TPJ, caudate - Positive ε₂: trials when adviser more helpful than predicted → precuneus, TPJ (anterior), fusiform gyrus - Positive ε₃ (high-level signed precision-weighted PE about adviser volatility) → septum, dorsal middle cingulate / dACC - Negative ε₃ → middle cingulate sulcus, paracentral lobule - Adviser fidelity (μ̂₂) during decision × follow advice → fusiform gyrus, middle cingulate - Adviser fidelity (μ̂₂) during decision × go against advice → left anterior insula, right TPJ, bilateral paracingulate cortex, bilateral dmPFC, right caudate - COMT Met/Met > Val/Val × ε₂ → ventral/dorsal striatum
- **key_regions:** Low-level social PE (ε₂) in dopaminergic midbrain (VTA/SN), ACC, bilateral insula, dmPFC, dlPFC, TPJ, caudate; high-level volatility PE (ε₃) in cholinergic septum and dorsal cingulate cortex; COMT-modulated ε₂ effects in ventral striatum.
- **key_regions_abbrev:** VS, caudate, striatum, mPFC, dmPFC, dlPFC, ACC, TPJ, insula, AI, midbrain, VTA
- **coordinates_peak:** fMRI study 1 — ε₂ (low-level PE): VTA/SN: 12, -18, -11 (R) ACC: 4, 36, 30 (R) dmPFC: -8, 26, 54 (L) Insula: 34, 18, -2 (R) Insula: -30, 27, 0 (L) Superior frontal cortex: -21, 38, 33 (L) dlPFC: -38, 21, 8 (L) dlPFC: 44, 15, 7 (R)  fMRI study 2 — ε₂ (low-level PE): VTA/SN: 4, -16, -10 (R) VTA/SN: -2, -20, -16 (L) TPJ: -34, -46, 42 (L) TPJ: 52, -50, 30 (R) Caudate: -8, 2, 10 (L) ACC: 2, 22, 28 (R) Middle temporal cortex: -44, -32, -8 (L) Superior temporal cortex: -40, -40, 2 (L) Insula: 32, 20, -4 (R) Insula: -32, 18, -4 (L) dmPFC: 0, 26, 54 (L) dmPFC: 4, 26, 60 (R) dlPFC: 48, 18, 4 (R)  Conjunction — ε₂: VTA/SN: 9, -15, -9 (R) Caudate: -8, 4, 9 (L) ACC: 8, 32, 27 (R) Insula: 36, 20, -2 (R) Insula: -38, 18, -5 (L) Middle frontal cortex: 33, 12, 49 (R) dmPFC: 6, 29, 54 (R) dlPFC: 42, 16, 7 (R)  fMRI study 1 — ε₃ (high-level PE): Septum: -5, 8, -7 (L) Dorsal middle cingulate cortex: 7, -12, 42 (R)  fMRI study 2 — ε₃ (high-level PE): Septum: -5, 12, -7 (L) Dorsal ACC: 6, 30, 28 (R)  Conjunction — ε₃: Septum: -5, 12, -7 (L) Dorsal ACC: 6, 30, 28 (R)  Supplementary Table 2 — positive ε₂: Study 1: TPJ: -40, -43, 27 (L); Middle temporal cortex: 40, -54, -3 (R); Fusiform gyrus: -28, -72, -8 (L) Study 2: Precuneus: 0, -58, 19 (L) Conjunction: Precuneus: 0, -58, 19 (L)  Supplementary Table 3 — negative ε₃: Study 1: SMA: 12, -22, 48 (R); Middle cingulate sulcus: 9, -13, 40 (R); Middle cingulate sulcus: -16, -43, 37 (L) Study 2: Middle cingulate sulcus: -8, -36, 62 (L); Paracentral lobule: 8, -24, 72 (R) Conjunction: Middle cingulate sulcus: 4, -19, 52 (R); Paracentral lobule: 8, -30, 57 (R)  COMT effects on ε₂: Study 1: Ventral striatum: -12, 8, -12 (L) Study 2: Dorsal striatum: -8, 10, -1 (L)
- **analysis_type:** both (whole-brain FWE-corrected + ROI with anatomical masks for VTA/SN and basal forebrain/septum)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N=82 total (Study 1: N=35; Study 2: N=47); all healthy male adults aged 19–30 (mean age = 25 ± 3.4); all right-handed. COMT distribution: Study 1: 8 Val/Val, 17 Val/Met, 10 Met/Met; Study 2: 10 Val/Val, 27 Val/Met, 9 Met/Met.
- **population_category:** healthy adults
- **population_age_range:** 19–30
- **ecological_validity:** Deception-free paradigm using pre-recorded video advice from real human advisers (recorded in prior interactive study). However, advice was not live/interactive, limiting recursive social inference to level 1 theory of mind. Male-only sample limits generalizability. Monetary incentive structure adds ecological validity to adviser motivation changes.
- **eligibility_flag:** 
- **concerns:** Male-only sample limits generalizability to female populations. Pre-recorded (not live) adviser limits depth of social inference. Study 2 was the placebo group from a pharmacological study, introducing potential expectancy effects. COMT effects in dlPFC did not replicate across studies. The two studies used different head coils (8-channel vs 32-channel), which may affect subcortical signal quality. fMRI activation in midbrain/septum does not definitively establish dopaminergic/cholinergic neurotransmitter involvement — these regions also contain glutamatergic and GABAergic neurons.
- **limitations_reported:** fMRI does not permit concluding with certainty that PE activations of midbrain and basal forebrain truly reflect activity of dopaminergic and cholinergic neurons respectively, as these regions also contain glutamatergic and GABAergic neurons; experimental design did not emphasize the recursive nature of social inference which is an important component of theory of mind — paradigm limited to level 1 theory of mind inference; pre-recorded advice may limit social cognition; conclusions restricted to a particular level of social inference and do not cover the full spectrum of theory of mind; differences in input structure and scanner hardware between the two studies may explain some discrepancies in high-level PE representations across studies
- **limitations_categorized:** limited ecological validity; restricted social inference depth; non-interactive paradigm; limited generalizability (male-only sample); indirect neurotransmitter inference from fMRI; hardware differences across studies
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 7.0
- **wc_total:** 7.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - effect_size: MEDIUM — most neural effects reported as t-scores; no standardized effect sizes (Cohen's d) for neural contrasts - wc_guidelines rule 3: MEDIUM — simulations used for optimizing stimulus input in study 2, but no formal model simulation/recovery analysis - wc_guidelines rule 8: MEDIUM — performance prediction analysis but no formal posterior predictive check - ecological_validity: MEDIUM — deception-free but non-interactive
- **cannot_find:** No formal parameter recovery or model recovery analyses; no Cohen's d or η² for neural contrasts; no individual subject behavioral data reported
- **other_notes:** This paper builds on and extends Diaconescu et al. (2014) with the same task paradigm adapted for pre-recorded video advice. The key novel contribution is linking hierarchical PEs to distinct neuromodulatory systems (dopamine for low-level PEs, acetylcholine for high-level PEs) in the social learning context, replicating across two independent samples. The TAPAS/HGF toolbox is publicly available. The study is notable for its rigorous replication design across two independent fMRI samples.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = general
- spec_locus = source+target+context
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_B_inference_modelling_others
- tax_mod_mentalizing_inference
- tax_model_HGF
- tax_model_bayesian
- tax_param_PE_signal
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_HGF
- tax_rr_model_family = HGF
- tax_rr_param_PE_signal
- tax_rr_param_precision
- tax_rr_primary_topic = advice_taking
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_advice_taking
- tax_rr_topic_mentalizing
- tax_social_nonsocial_comparison
- tax_topic_advice_taking
- tax_topic_mentalizing
