# Sul et al. (2015)

- **study_id:** `a0dbe04cafc314aa9_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Sul, S., Tobler, P. N., Hein, G., Leiberg, S., Jung, D., Fehr, E., & Kim, H. (2015). Spatial gradient in value representation along the medial prefrontal cortex reflects individual differences in prosociality. *Proceedings of the National Academy of Sciences*, *112*(25), 7851–7856. https://doi.org/10.1073/pnas.1423895112
- **citation_short:** Sul et al. (2015)
- **doi:** 10.1073/pnas.1423895112
- **publication_type:** peer-reviewed journal
- **year:** 2015.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofPsychology,KoreaUniversity,Seoul136-701,RepublicofKorea;bDepartmentofEconomics,UniversityofZurich,CH-8006Zurich,; etheimportanceofvaluinganotherperson’swelfareforpro- neural processes associated with self- and other-regarding valua-; DepartmentofBrainandCognitiveEngineering,KoreaUniversity,Seoul136-701,RepublicofKorea; University,Princeton,NJ,andapprovedMay5,2015(receivedforreviewDecember13,2014); ether the occurrence of a response increases when it is fol-; mited understanding of tioninacomparable,principledway; ethedurationofthenoiseforthemselvesand/orthe; lableonlinethroughthePN
- **code_url:** 

## Computational level
- **study_focus:** Prosocial learning — how individuals learn to benefit others through instrumental conditioning, and how spatial organization of value signals in MPFC relates to individual differences in prosociality.
- **study_focus_short:** Prosocial learning
- **learning_mode_description:** - Learning mode: Learning from one's own reward/punishment outcomes about action values for self and/or another person   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (points earned to reduce aversive noise)   - Learning about:     - Target type (social): other (stranger partner) — in OTHER condition       - If joint: **joint** — in BOTH condition (self + other)     - Target content (social): outcome (noise reduction for other)     - Target type (non-social): self — in SELF condition     - Target content (non-social): outcome (noise reduction for self)
- **task_description:** In each trial, participants chose between two fractal images associated with different reward probabilities (70% vs. 30%) to earn points that reduced aversive noise duration for themselves (SELF condition), for both themselves and a stranger partner (BOTH condition), or for the partner only (OTHER condition). The scanned participant learned choice-outcome associations across 144 trials (48 per condition) via trial-and-error.
- **task_paradigm:** Prosocial choice task
- **players:** Single agent (participant), dyadic (stranger partner outside scanner)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Abstract fractal images, binary feedback (points/no points), aversive noise
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - Participants learned to choose the high reward probability option above chance in all conditions, including OTHER (t(25) = 2.68, p < 0.05)   - Spatial gradient within MPFC: ventral MPFC encoded self-regarding values, dorsal MPFC encoded other-regarding values (condition x ROI interaction: F(4,100) = 4.49, p < 0.005)   - Selfish individuals showed steeper spatial gradient (greater self-other segregation) than prosocial individuals (F(1,23) = 6.72, p < 0.05; three-way interaction group x condition x ROI: F(4,92) = 3.10, p < 0.05)   - Spatial gradient slope correlated with choice behavior in OTHER condition (r = -0.55, p < 0.01; r = -0.43, p < 0.05 without outlier)   - Prosocial individuals showed stronger MPFC-striatum functional connectivity during OTHER vs. SELF choices (all F(1,23) > 9.98, all p < 0.01 for three MPFC seeds)   - Selfish individuals showed greater AI/IFG activation for OTHER vs. SELF (Z = 3.65 at x=36, y=26, z=-4)   - AI/IFG activation negatively correlated with DMPFC-striatum coupling (r = -0.48, p = 0.01) and MMPFC-striatum coupling (r = -0.47, p = 0.01)
- **effect_size:** r = -0.55 (gradient slope vs. OTHER condition choice); r = -0.43 (same, outlier removed); eta-squared not reported; F-statistics provided above
- **learning_from:** Self; own reward outcomes (points to reduce aversive noise duration)
- **learning_about:** Other (stranger partner) — welfare/noise reduction; self — welfare/noise reduction  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Advantage learning model (2 free params per condition: alpha, beta; separate fits for SELF, BOTH, OTHER)
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Advantage learning model", "family": "Rescorla-Wagner / temporal difference", "n_params": 2, "metric": "MLE (log-likelihood)"}]
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate): mean fitted values: alpha_SELF = 0.55, alpha_BOTH = 0.49, alpha_OTHER = 0.39 - beta (inverse temperature): mean fitted values: beta_SELF = 0.52, beta_BOTH = 0.44, beta_OTHER = 0.57 - s (experienced reward magnitude; used for prosociality classification only): estimated between -2 and 2 with increment of 1, determined by MLE [S]
- **social_param:** s — experienced magnitude of reward outcome, estimated separately for SELF, BOTH, and OTHER conditions. Comparison of s_SELF vs. s_OTHER determines prosocial vs. selfish classification. [S]
- **social_param_name:** s
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** MLE (log-likelihood); no formal model comparison between competing models reported (only one model tested)
- **how_model_fit:** individual-level-fit (parameters estimated separately per condition per individual via maximum likelihood)
- **data_type_fit_to:** choice behavior

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) + PPI
- **contrast:** - Parametric modulation of chosen value at option presentation across SELF, BOTH, OTHER conditions (MPFC: x=4, y=52, z=8) - Parametric modulation of RPE at outcome presentation (bilateral ventral striatum) - SELF vs. OTHER chosen value parametric modulators within MPFC ROIs (spatial gradient analysis) - PPI: VMPFC/MMPFC/DMPFC seeds x OTHER vs. SELF at option presentation (striatum target) - OTHER vs. SELF contrast at option presentation: selfish > prosocial (AI/IFG: x=36, y=26, z=-4)
- **key_regions:** Self-regarding value in VMPFC; other-regarding value in DMPFC; spatial gradient along MPFC reflects prosociality; RPE in bilateral ventral striatum; prosocial individuals show stronger MPFC-striatum coupling for other-regarding choices; selfish individuals recruit AI/IFG for other-regarding decisions.
- **key_regions_abbrev:** VS, striatum, vmPFC, mPFC, dmPFC, AI, IFG
- **coordinates_peak:** Chosen value across conditions: MPFC: 4, 52, 8 (R) Chosen value SELF: MPFC: 0, 56, 2 (L/R) Chosen value BOTH: MPFC: 8, 54, 8 (R) Chosen value OTHER: MPFC/ACC: 2, 44, 12 (L/R) RPE across conditions: Ventral Striatum: -12, 14, -4 (L) RPE across conditions: Ventral Striatum: 8, 10, -4 (R) RPE across conditions: Precuneus: 2, -68, 40 (L/R) RPE across conditions: Inferior Parietal Lobule: -44, -50, 46 (L) RPE across conditions: ACC: -8, 42, 12 (L) RPE across conditions: Inferior Parietal Lobule: 40, -56, 44 (R) PPI VMPFC seed > striatum (prosocial > selfish): Ventral Striatum: 16, 20, 0 (R) PPI MMPFC seed > striatum (prosocial > selfish): Striatum: 6, 14, 2 (R) PPI DMPFC seed > striatum (prosocial > selfish): Striatum: 14, 18, 4 (R) OTHER > SELF selfish > prosocial: AI/IFG: 36, 26, -4 (R) OTHER > SELF selfish > prosocial: DLPFC: 38, 16, 40 (R) OTHER > SELF selfish > prosocial: DLPFC: -48, 10, 38 (L) OTHER > SELF selfish > prosocial: AI: -34, 22, 0 (L) OTHER > SELF selfish > prosocial: dACC: 6, 38, 22 (R)
- **analysis_type:** both (ROI-based for MPFC spatial gradient and PPI; whole-brain for group comparisons and RPE)  ---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 30 pairs (60 total); 26 scanned participants analyzed after exclusions (4 excluded for head movement/random responding); ages 19-29 (mean 21.9); all female.
- **population_category:** healthy adults
- **population_age_range:** 19–29
- **ecological_validity:** Low-moderate. Task uses abstract fractal stimuli and aversive noise rather than real social interactions. Prosocial behavior is operationalized as instrumental learning to reduce noise for a stranger, which is a simplified proxy for real-world prosociality. However, the paradigm does involve real consequences for a real partner. Same-sex (all female) pairs limit generalizability.
- **eligibility_flag:** 
- **concerns:** - Only one computational model tested (no model comparison). - Small sample size (N=26 after exclusions; prosocial n=15, selfish n=10). - All-female sample limits generalizability. - Median split of prosocial vs. selfish groups based on model parameter (s) is somewhat arbitrary; continuous analyses partially address this. - No parameter recovery or model recovery analyses. - The advantage learning model parameters were estimated separately per condition, meaning no single model captures cross-condition learning. - Some fMRI results reported at lenient thresholds (p < 0.005 uncorrected for some analyses).
- **limitations_reported:** Authors acknowledge: fMRI spatial resolution is far lower than animal neurophysiology; exact nature of additional cognitive processes used by selfish individuals merits further investigation; findings have yet to be tested with more direct measures of altruism; cannot completely rule out that AI/IFG activation may reflect aversive response to other-regarding choices among selfish individuals rather than cognitive effort.
- **limitations_categorized:** limited spatial resolution; limited ecological validity; limited generalizability (all-female sample); alternative explanations not fully ruled out; sample size
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
- **flagged_fields:** - model_comparison_metric: MEDIUM — only one model tested; no formal model comparison. Log-likelihood used for parameter fitting, not model selection. - all_models_tested: MEDIUM — only one model was fitted; no competing models compared. - effect_size: MEDIUM — mostly F-statistics and correlation coefficients reported; no standardized effect sizes like Cohen's d.
- **cannot_find:** - No competing models were tested; only the advantage learning model was used. - No BIC/AIC/formal model comparison metrics reported. - No parameter recovery or model recovery analyses reported.  ---  ## IMPLEMENTATION LEVEL
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
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_PE_signal
- tax_rr_param_social_weight
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_topic_prosocial_altruism
- tax_social_nonsocial_comparison
- tax_topic_prosocial_altruism
