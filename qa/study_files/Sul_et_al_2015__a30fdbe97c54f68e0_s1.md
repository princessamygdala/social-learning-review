# Sul et al. (2015)

- **study_id:** `a30fdbe97c54f68e0_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Sul, S., Tobler, P. N., Hein, G., Leiberg, S., Jung, D., Fehr, E., & Kim, H. (2015). Spatial gradient in value representation along the medial prefrontal cortex reflects individual differences in prosociality. *Proceedings of the National Academy of Sciences, 112*(25), 7851–7856. https://doi.org/10.1073/pnas.1423895112
- **citation_short:** Sul et al. (2015)
- **doi:** 10.1073/pnas.1423895112
- **publication_type:** peer-reviewed journal
- **year:** 2015.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofPsychology,KoreaUniversity,Seoul136-701,RepublicofKorea;bDepartmentofEconomics,UniversityofZurich,CH-8006Zurich,; etheimportanceofvaluinganotherperson’swelfareforpro- neural processes associated with self- and other-regarding valua-; DepartmentofBrainandCognitiveEngineering,KoreaUniversity,Seoul136-701,RepublicofKorea; University,Princeton,NJ,andapprovedMay5,2015(receivedforreviewDecember13,2014); ether the occurrence of a response increases when it is fol-; mited understanding of tioninacomparable,principledway; ethedurationofthenoiseforthemselvesand/orthe; lableonlinethroughthePN
- **code_url:** 

## Computational level
- **study_focus:** Prosocial learning — how self- vs. other-regarding values are learned via reinforcement and how their neural representation relates to individual differences in prosociality.
- **study_focus_short:** Prosocial learning
- **learning_mode_description:** - Learning mode: Learning from one's own reward/punishment outcomes about the value of choices that benefit self and/or another person   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (points reducing aversive noise duration)   - Learning about:     - Target type (social): other (stranger partner)       - Also self (SELF condition) and joint self+other (BOTH condition)     - Target content (social): outcome (welfare/noise reduction for other)
- **task_description:** Participants chose between two fractal images associated with different reward probabilities (70% vs. 30%) across three conditions (SELF, BOTH, OTHER) to earn points that reduced aversive noise duration for themselves and/or a stranger partner outside the scanner. They learned choice-outcome associations by trial and error over 144 trials.
- **task_paradigm:** Prosocial choice task
- **players:** Single agent (scanned participant), dyadic (stranger female partner outside scanner)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Fractal images (abstract), binary outcome feedback (points or no points), aversive noise
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - Participants chose HRP option above chance in OTHER condition (t(25) = 2.68, p < 0.05)   - Spatial gradient: condition x ROI location interaction in MPFC (F(4,100) = 4.49, p < 0.005)   - Prosocial vs. selfish group: three-way interaction group x condition x ROI (F(4,92) = 3.10, p < 0.05)   - Selfish group showed steeper spatial gradient than prosocial group (F(1,23) = 6.72, p < 0.05)   - Spatial gradient slope correlated with OTHER condition HRP choice (r = -0.55, p < 0.01; r = -0.43 excluding outlier)   - Prosocial group: stronger MPFC-striatum PPI connectivity in OTHER vs. SELF (all F(1,23) > 9.98, all p < 0.01)   - AI/IFG activation: selfish > prosocial in OTHER vs. SELF (Z = 3.65)   - AI/IFG activation correlated with RTs (r = 0.50, p < 0.05)   - AI/IFG activation negatively correlated with DMPFC-striatum coupling (r = -0.48, p = 0.01) and MMPFC-striatum coupling (r = -0.47, p = 0.01)   - Model-based prosociality grouping validated by self-report SVO (Fisher's exact p < 0.05; chi-square(1) = 5.66, p < 0.05)
- **effect_size:** - Main Results:   - Participants chose HRP option above chance in OTHER condition (t(25) = 2.68, p < 0.05)   - Spatial gradient: condition x ROI location interaction in MPFC (F(4,100) = 4.49, p < 0.005)   - Prosocial vs. selfish group: three-way interaction group x condition x ROI (F(4,92) = 3.10, p < 0.05)   - Selfish group showed steeper spatial gradient than prosocial group (F(1,23) = 6.72, p < 0.05)   - Spatial gradient slope correlated with OTHER condition HRP choice (r = -0.55, p < 0.01; r = -0.43 excluding outlier)   - Prosocial group: stronger MPFC-striatum PPI connectivity in OTHER vs. SELF (all F(1,23) > 9.98, all p < 0.01)   - AI/IFG activation: selfish > prosocial in OTHER vs. SELF (Z = 3.65)   - AI/IFG activation correlated with RTs (r = 0.50, p < 0.05)   - AI/IFG activation negatively correlated with DMPFC-striatum coupling (r = -0.48, p = 0.01) and MMPFC-striatum coupling (r = -0.47, p = 0.01)   - Model-based prosociality grouping validated by self-report SVO (Fisher's exact p < 0.05; chi-square(1) = 5.66, p < 0.05)
- **learning_from:** Self; own reward outcomes (points earned from chosen option)
- **learning_about:** Other (stranger partner); value of choices benefiting other's welfare (noise reduction)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Advantage learning model (2 free params per condition: α, β; plus reward magnitude parameter s for prosociality classification)
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Advantage learning model", "family": "Temporal difference / Rescorla-Wagner", "n_params": 2, "metric": "MLE (log likelihood)"}] - Note: Only one model tested. No model comparison performed.
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): mean fitted values: SELF = 0.55, BOTH = 0.49, OTHER = 0.39 - β (inverse temperature): mean fitted values: SELF = 0.52, BOTH = 0.44, OTHER = 0.57 - s (experienced reward magnitude) [S]: estimated between -2 to 2 with increment of 1; used to classify prosocial (s_SELF ≤ s_OTHER) vs. selfish (s_SELF > s_OTHER) groups
- **social_param:** s — experienced reward magnitude parameter, estimated separately for SELF, BOTH, and OTHER conditions. The ratio s_SELF vs. s_OTHER indexes prosocial propensity.
- **social_param_name:** s
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** MLE (log likelihood); no formal model comparison (single model)
- **how_model_fit:** individual-level-fit (parameters estimated separately for each condition for each individual via maximum likelihood)
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) + PPI
- **contrast:** - Chosen value (parametric modulator at option presentation) across SELF, BOTH, OTHER conditions - Chosen value for SELF condition only - Chosen value for OTHER condition only - RPE (parametric modulator at outcome phase) across conditions - PPI: VMPFC/MMPFC/DMPFC seed × OTHER vs. SELF at option presentation - OTHER vs. SELF at option presentation: selfish > prosocial group (two-sample t-test)
- **key_regions:** Self-regarding value in VMPFC; other-regarding value in DMPFC; RPE in bilateral ventral striatum; prosocial individuals show stronger MPFC-striatum PPI coupling for OTHER vs. SELF; selfish individuals show greater AI/IFG activation for OTHER vs. SELF.
- **key_regions_abbrev:** VS, striatum, vmPFC, mPFC, dmPFC, AI, IFG
- **coordinates_peak:** Chosen value across conditions — MPFC: 4, 52, 8 (R) Chosen value SELF — MPFC: 0, 56, 2 (L/R) Chosen value BOTH — MPFC: 8, 54, 8 (R) Chosen value OTHER — MPFC/ACC: 2, 44, 12 (L/R) RPE across conditions — Precuneus: 2, -68, 40 (L/R) RPE across conditions — IPL: -44, -50, 46 (L) RPE across conditions — Ventral Striatum: -12, 14, -4 (L) RPE across conditions — Ventral Striatum: 8, 10, -4 (R) RPE across conditions — ACC: -8, 42, 12 (L) RPE across conditions — IPL: 40, -56, 44 (R) PPI VMPFC seed — Striatum group diff: 16, 20, 0 PPI MMPFC seed — Striatum group diff: 6, 14, 2 PPI DMPFC seed — Striatum group diff: 14, 18, 4 AI/IFG (selfish > prosocial, OTHER vs. SELF): 36, 26, -4 (R) DLPFC (selfish > prosocial): 38, 16, 40 (R) DLPFC (selfish > prosocial): -48, 10, 38 (L) Anterior Insula (selfish > prosocial): -34, 22, 0 (L) dACC (selfish > prosocial): 6, 38, 22 (R)
- **analysis_type:** both (ROI for MPFC value gradient and striatum RPE using anatomical masks via AAL atlas; whole-brain for group comparison of OTHER vs. SELF contrasts)  ---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 30 pairs (30 scanned), 4 excluded for head motion/random responding; N = 26 included in fMRI analysis. All female, mean age 21.9 years (range 19–29). Prosocial group n = 15, selfish group n = 10 (1 excluded from group analyses).
- **population_category:** healthy adults
- **population_age_range:** 19–29
- **ecological_validity:** Low-moderate. Task uses abstract fractal stimuli and aversive noise reduction rather than real social interaction. Partner is a stranger with no direct interaction. Prosocial behavior is operationalized as instrumental learning to reduce noise for another, which is somewhat artificial but does involve real consequences for a real person.
- **eligibility_flag:** 
- **concerns:** - Only one computational model tested — no model comparison - Small sample size (N = 26 in fMRI; group split: 15 vs. 10) - All-female sample limits generalizability - Prosocial/selfish group classification based on a discrete parameter (s) estimated from the same data — potentially circular when relating to behavior - Reward magnitude parameter s constrained to integer values [-2, 2] with increment of 1 — very coarse - Some thresholds lenient (p < 0.005 uncorrected for some analyses, p < 0.05 uncorrected for ROI definition) - No correction for multiple correlations across brain-behavior analyses
- **limitations_reported:** Authors acknowledge: fMRI spatial resolution is far lower than animal neurophysiological studies; cannot completely rule out that AI/IFG activation reflects aversive response rather than cognitive control; the exact nature of additional cognitive processes used by selfish individuals merits further investigation; findings have yet to be tested with more direct measures of altruism.
- **limitations_categorized:** limited spatial resolution; alternative explanation not fully ruled out; limited ecological validity; limited generalizability (all-female sample); small sample size  ---  ## WC CHECKLIST  1. Design a good experiment: **Yes** — task with three conditions (SELF, BOTH, OTHER) specifically designed to isolate self- vs. other-regarding learning 2. Design good models: **No** — only one model tested, no competing hypotheses 3. Simulate, simulate, simulate: **No** — no simulation described 4. Fit the parameters: **Yes** — MLE fitting of parameters individually 5. Check parameter recovery: **No** — no parameter recovery reported 6. Check model recovery: **No** — only one model, no confusion matrix 7. Fit real data and compare models: **No** — only one model, no comparison 8. Validate the winning model: **Partial** — model-based prosociality classification validated against self-report SVO questionnaire, but no posterior predictive checks 9. Analyze the winning model: **Yes** — model parameters used as regressors in fMRI, and s parameter used to classify groups 10. Report results transparently: **Partial** — mean parameter values reported; no mention of shared data/code
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 4.0
- **wc_total:** 4.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_neural = dedicated
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_topic_prosocial_altruism
- tax_topic_prosocial_altruism
