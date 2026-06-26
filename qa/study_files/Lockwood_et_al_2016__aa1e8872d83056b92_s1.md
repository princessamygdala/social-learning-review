# Lockwood et al. (2016)

- **study_id:** `aa1e8872d83056b92_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Lockwood, P. L., Apps, M. A. J., Valton, V., Viding, E., & Roiser, J. P. (2016). Neurocomputational mechanisms of prosocial learning and links to empathy. *Proceedings of the National Academy of Sciences*, *113*(35), 9763–9768. https://doi.org/10.1073/pnas.1603198113
- **citation_short:** Lockwood et al. (2016)
- **doi:** 10.1073/pnas.1603198113
- **publication_type:** peer-reviewed journal (pnas)
- **year:** 2016.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DivisionofPsychologyandLanguageSciences,UniversityCollegeLondon,LondonWC1H6BT,UnitedKingdom;bDepartmentofExperimentalPsychology,; UniversityofOxford,OxfordOX13UD,UnitedKingdom;andcInstituteofCognitiveNeuroscience,UniversityCollegeLondon,LondonWC1N3AZ,; UniversityofZurich,Zurich,Switzerland,andacceptedbyEditorialBoardMemberSusanT
- **code_url:** 

## Computational level
- **study_focus:** Prosocial learning — how people learn to obtain rewards for others vs. self vs. no one, and links to trait empathy.
- **study_focus_short:** Prosocial learning
- **learning_mode_description:** Source is non-social (self making choices), target is social (other person receiving rewards). Correctly tagged.
- **task_description:** Participants chose between two abstract symbols with different reward probabilities (75% vs. 25%) across three conditions — for self, for another participant (prosocial), or for no one (control) — learning stimulus-reward associations through trial-and-error feedback. The task was performed during fMRI with 144 trials (48 per condition, 3 blocks of 16 per condition).
- **task_paradigm:** Prosocial choice task
- **players:** Single agent (participant), single target (anonymous male confederate believed to be another participant)
- **n_players:** single agent (1)
- **partner_type:** confederate
- **stimuli:** Abstract symbols (Agathodaimon font letters), binary outcomes (100 points / 0 points), condition labels ("you" / confederate name / "no one")
- **method:** fMRI / behavioural
- **method_full:** fMRI (model-based fMRI with parametric regressors) + behavioural computational modeling
- **main_result:** - Main Results:   - Main effect of condition on learning rate: F(2,60) = 11.47, p < .001   - Self > prosocial learning rate (d = 0.87, p < .001)   - Self > no one learning rate (d = 0.53, p = .01)   - Prosocial vs. no one learning rate n.s. (d = 0.25, p = .18)   - Main effect of condition on choice variability (β): F(2,60) = 7.87, p < .001   - No one > self choice variability (d = 0.46, p = .017); No one > prosocial (d = 0.58, p = .003); Self vs. prosocial n.s. (d = 0.24, p = .20)   - Online simulation empathy subscale correlated with prosocial–self learning rate difference (r = 0.44, p = .01, 95% CI [0.18, 0.66])   - Online simulation correlated with prosocial–self PE response in sgACC (r = 0.39, p = .03, 95% CI [0.13, 0.60])   - Bayesian model comparison: full RL model > null model (ΔBIC > 600); full > fixed-parameter model (ΔBIC > 10)   - VS coded PEs in all three conditions (conjunction: right VS [10, 15, −9], Z = 4.09, k = 91, p = .006 SVC-FWE; left VS [−12, 10, −11], Z = 3.72, k = 78, p = .023 SVC-FWE)   - sgACC exclusively coded prosocial PEs ([−2, 4, −15], Z = 3.83, k = 148, p = .019 SVC-FWE)   - DLPFC coded self + no one > prosocial PEs (left [−36, 18, 43], Z = 4.47, k = 62, p = .006 SVC-FWE; right [32, 15, 39], Z = 4.36, k = 27, p = .020 SVC-FWE)
- **effect_size:** - Main Results:   - Main effect of condition on learning rate: F(2,60) = 11.47, p < .001   - Self > prosocial learning rate (d = 0.87, p < .001)   - Self > no one learning rate (d = 0.53, p = .01)   - Prosocial vs. no one learning rate n.s. (d = 0.25, p = .18)   - Main effect of condition on choice variability (β): F(2,60) = 7.87, p < .001   - No one > self choice variability (d = 0.46, p = .017); No one > prosocial (d = 0.58, p = .003); Self vs. prosocial n.s. (d = 0.24, p = .20)   - Online simulation empathy subscale correlated with prosocial–self learning rate difference (r = 0.44, p = .01, 95% CI [0.18, 0.66])   - Online simulation correlated with prosocial–self PE response in sgACC (r = 0.39, p = .03, 95% CI [0.13, 0.60])   - Bayesian model comparison: full RL model > null model (ΔBIC > 600); full > fixed-parameter model (ΔBIC > 10)   - VS coded PEs in all three conditions (conjunction: right VS [10, 15, −9], Z = 4.09, k = 91, p = .006 SVC-FWE; left VS [−12, 10, −11], Z = 3.72, k = 78, p = .023 SVC-FWE)   - sgACC exclusively coded prosocial PEs ([−2, 4, −15], Z = 3.83, k = 148, p = .019 SVC-FWE)   - DLPFC coded self + no one > prosocial PEs (left [−36, 18, 43], Z = 4.47, k = 62, p = .006 SVC-FWE; right [32, 15, 39], Z = 4.36, k = 27, p = .020 SVC-FWE)
- **learning_from:** Self; own choice outcomes (reward/no reward for chosen symbol). Source: self.
- **learning_about:** Other (confederate); which stimulus to choose to maximize reward for another person. Target: other / self / no one (condition-dependent).  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** RW with separate α and β per condition (α_self, α_prosocial, α_noone; β_self, β_prosocial, β_noone); 6 free parameters. Q_{t+1}(a) = Q_t(a) + α × [r_t − Q_t(a)]; softmax choice rule with temperature β.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "Full RL model (separate α, β per condition)", "family": "Rescorla-Wagner", "n_params": 6, "metric": "BIC"} 2. {"name": "Null model (α = 0, β free)", "family": "Random/null", "n_params": 1, "metric": "BIC"} 3. {"name": "Fixed RL model (single α, β across conditions)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BIC"}
- **model_mb_mf:** MF
- **model_params:** - α_self [learning rate, self condition]: controls extent value is updated by PE for self trials. Mean fitted value not explicitly reported in text. - α_prosocial [S] [learning rate, prosocial condition]: learning rate when obtaining rewards for another. Mean ~0.2 (from figure; exact value not stated in text). - α_noone [learning rate, no one condition]: learning rate for control condition. - β_self [temperature, self condition]: choice variability for self. - β_prosocial [S] [temperature, prosocial condition]: choice variability for prosocial. - β_noone [temperature, no one condition]: choice variability for no one.
- **social_param:** α_prosocial — learning rate specific to prosocial condition; captures speed of learning when rewards go to another person. Higher values = faster prosocial learning.
- **social_param_name:** α_prosocial
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (Bayesian Information Criterion); ΔBIC > 10 = decisive evidence.
- **how_model_fit:** individual-level-fit (MAP — maximum a posteriori; two-stage: MLE then re-estimation with Gaussian priors derived from group MLE distribution)
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — PEs from computational model used as parametric modulators at outcome onset; chosen value as parametric modulator at cue onset. ROI-based SVC analysis with anatomically defined masks.
- **contrast:** - Conjunction null: self PE ∩ prosocial PE ∩ no one PE → bilateral VS - Prosocial PE > self PE + no one PE → sgACC - Self PE + no one PE > prosocial PE → bilateral DLPFC - Self PE > prosocial PE + no one PE → no suprathreshold voxels - No one PE > self PE + prosocial PE → parahippocampal gyrus (uncorrected) - Prosocial PE > self PE (without control) → sgACC - Self PE > prosocial PE (without control) → thalamus, MFG, cerebellum - Correlation: online simulation × (prosocial – self) PE → sgACC (r = .39)
- **key_regions:** Common PE signal in bilateral ventral striatum across all conditions; prosocial-specific PE in sgACC/basal forebrain; self/no one > prosocial PE in bilateral DLPFC. Empathy (online simulation) modulated prosocial PE selectivity in sgACC.
- **key_regions_abbrev:** VS, striatum, dlPFC, ACC, sgACC, AI
- **coordinates_peak:** *Conjunction (all PEs) — SVC-FWE corrected:* - Right ventral striatum (caudate): 10, 15, −9 (Z = 4.09, k = 91) - Left ventral striatum (putamen): −12, 10, −11 (Z = 3.72, k = 78)  *Prosocial PE > self + no one — SVC-FWE corrected:* - sgACC/basal forebrain: −2, 4, −15 (Z = 3.83, k = 148)  *Self + no one PE > prosocial PE — SVC-FWE corrected:* - Left DLPFC (MFG): −36, 18, 43 (Z = 4.47, k = 62) - Right DLPFC: 32, 15, 39 (Z = 4.36, k = 27)  *Additional from Table S2 (P < .001 uncorrected, k ≥ 100):* - sgACC/basal forebrain (prosocial > self+noone): 0, 6, −15 (Z = 3.87, k = 182) - Left MFG (self+noone > prosocial): −36, 18, 43 (Z = 4.47, k = 347) - Left IFG: −54, 39, −3 (Z = 4.06, k = 190) - Left SMG: −58, −46, 33 (Z = 3.77, k = 124) - Left STG: −58, −28, −2 (Z = 3.77, k = 114) - Left IPL: −64, −36, 39 (Z = 3.77, k = 136) - Left MFG: −50, 39, 24 (Z = 3.56, k = 298) - Right SFG: 42, 39, 36 (Z = 3.51, k = 184) - Left parahippocampal gyrus (noone > self+prosocial): −26, −55, −8 (Z = 4.35, k = 320)  *Whole-brain FWE (Table S1) — Main effect PE:* - Right caudate: 10, 15, −9 (Z = 6.92, k = 694) - Right putamen: 20, 9, −11 (Z = 6.36) - Left putamen: −10, 9, −11 (Z = 6.65, k = 605) - Left MTG: −40, −66, 24 (Z = 6.31, k = 399) - Left MFG: −26, 20, 52 (Z = 5.57, k = 102) - Left PCC sulcus: −10, −42, 37 (Z = 5.56, k = 854) - Left amygdala: −26, −4, −21 (Z = 5.40, k = 67)  *Self PE (Table S1):* - Right putamen: 18, 6, −8 (Z = 6.02, k = 226) - Left putamen: −12, 8, −11 (Z = 5.22, k = 104)  *Prosocial PE (Table S1):* - Right caudate: 8, 12, −11 (Z = 5.02, k = 30) - Left sgACC/basal forebrain: −6, 15, −8 (Z = 4.95, k = 12)  *Exploratory DMPFC (supplement, uncorrected):* - Left DMPFC: −6, 32, 46 (Z = 3.45, k = 10) - Right DMPFC: 16, 64, 16 (Z = 3.21, k = 11)
- **analysis_type:** both (whole-brain + ROI) — correctly identified.
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 31 (34 recruited, 3 excluded: 2 at chance performance, 1 neurological abnormality on MRI); all right-handed healthy males, ages 19–32 (M = 22.7, SD = 3.0). 80% power to detect d = 0.52 at α = .05 two-tailed.
- **population_category:** healthy adults
- **population_age_range:** 19–32
- **ecological_validity:** Low-moderate. Task uses abstract symbols and probabilistic learning, which lacks naturalistic social interaction. The "other person" was a confederate (deception); participants never directly interacted with them. Choices were anonymous. Only males tested.
- **eligibility_flag:** 
- **concerns:** - Only male participants; limits generalizability - Deception paradigm — confederate posed as another participant - Flat payoff (all paid same amount due to ethics) may reduce incentive alignment - Mean fitted parameter values for α and β not numerically reported in text (only shown in figures) - No parameter recovery or model recovery reported - No posterior predictive checks reported - sgACC and VS ROI masks had small overlap (authors acknowledge this but state significant activations were non-overlapping) - 1.5T scanner (lower field strength) - dACC showed no significant responses in any contrast — null finding difficult to interpret
- **limitations_reported:** Given potential gender differences in empathy and prosocial behavior, our sample in this study was composed only of males. Future studies would benefit from also examining prosocial learning in females"; null finding in anterior insula and dACC may be due to different reference frames (self-action vs. observation) compared to prior empathy studies; the sgACC region is heterogeneous and future high-resolution fMRI needed to dissociate subregions; longitudinal developmental and twin studies needed to determine heritability of sgACC prosocial specificity.
- **limitations_categorized:** limited generalizability (male-only sample); task simplicity (abstract stimuli, no direct social interaction); limited ecological validity; potential deception effects; low field strength scanner; no parameter recovery; no model recovery; no posterior predictive check
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.0
- **wc_total:** 5.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM — mean fitted values for α and β not numerically reported in text, only visible in figures - effect_size for learning rates: HIGH — Cohen's d reported directly - empathy correlations: HIGH — r values and CIs reported - coordinates: HIGH — reported in main text and supplement tables
- **cannot_find:** - Exact mean fitted parameter values for α and β (only graphically displayed) - No parameter recovery analysis - No model recovery/confusion matrix - No posterior predictive check details - No data/code sharing statement found
- **other_notes:** This is Patricia Lockwood's own 2016 PNAS paper. The task design has become influential as a paradigm for studying prosocial learning. The sgACC finding for prosocial-specific PEs has been replicated and extended in subsequent work. The empathy link (online simulation subscale of QCAE) provides individual difference evidence. The "no one" control condition is a methodological strength, controlling for fictive PEs.  ---  ## WC GUIDELINES  1. **Design a good experiment**: Yes — task specifically designed to isolate prosocial learning with appropriate self and no-one controls 2. **Design good models**: Partial — only 3 models compared (full RL, null, fixed-parameter); no alternative model families (e.g., Bayesian, asymmetric learning rates) 3. **Simulate, simulate, simulate**: No — no mention of model simulation before fitting 4. **Fit the parameters**: Yes — MAP estimation (two-stage MLE then MAP with Gaussian priors) 5. **Check parameter recovery**: No — not reported 6. **Check model recovery**: No — not reported 7. **Fit real data and compare models**: Yes — BIC comparison across three models, ΔBIC > 10 decisive evidence 8. **Validate the winning model**: No — no posterior predictive check or model validation reported 9. **Analyze the winning model**: Yes — parameters compared across conditions; individual differences in learning rate correlated with empathy; PE regressors used in fMRI 10. **Report results transparently**: Partial — no data/code sharing statement found; parameter means not numerically reported
- **re_extract_flag:** false (full text and supplement accessed)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
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
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_secondary_topic = empathy_vicarious
- tax_rr_topic_empathy_vicarious
- tax_rr_topic_prosocial_altruism
- tax_topic_empathy_vicarious
- tax_topic_prosocial_altruism
