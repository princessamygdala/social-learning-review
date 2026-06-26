# Haaker & Olsson (2018)

- **study_id:** `a661fc88f8387f952_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Lindstr\u00f6m, B., Haaker, J., & Olsson, A. (2018). A common neural network differentially mediates direct and social fear learning. *NeuroImage*, *167*, 121--129. https://doi.org/10.1016/j.neuroimage.2017.11.039
- **citation_short:** Haaker & Olsson (2018)
- **doi:** 10.1016/j.neuroimage.2017.11.039
- **publication_type:** peer-reviewed journal
- **year:** 2018.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** ethecross-speciesimportanceofsocialfearlearning,itsneural This situation mirrors the ongoing debate within the wider field of; LaboratoryforSocialandNeuralSystemsResearch,DepartmentofEconomics,UniversityofZurich,Zurich,Switzerland; ethesitewhereinforma- neuralunderpinningsofsocialfearlearningbyinvestigatingsharedand; SectionforPsychology,DepartmentofClinicalNeuroscience,KarolinskaInstitutet,Sweden; DepartmentofSystemsNeuroscience,UniversityMedicalCenterHamburg-Eppendorf,Germany; centeredontheamygdala,theanteriorinsula(AI),; lableonline21November2017; lableatScienceDirect; emails: bjorn.r.linds
- **code_url:** 

## Computational level
- **study_focus:** Social fear learning / observational fear conditioning -- comparing direct (Pavlovian) and social (observational) fear learning within the same participants, examining shared and unique neural and computational mechanisms.
- **study_focus_short:** Social fear learning / observational fear conditioning -- comparing direct
- **learning_mode_description:** - Learning mode: Learning from observing another's aversive outcome about threat associations between conditioned stimuli and aversive events   - Learning from:     - Source type (social): other (demonstrator)     - Source content (social): outcome (observed shock / aversive US)   - Learning about:     - Target type (non-social): world (CS-US contingency)     - Target content (non-social): stimulus (conditioned stimulus threat value)  Note: The paper has two phases (direct and social) but these are conditions within a single study, not separate studies. The social learning phase is the one relevant to this review. However, the direct phase serves as comparison. This is one study with one row.
- **task_description:** Participants underwent two counterbalanced fear learning phases (direct and social). In the direct phase, one colored square (CS+) was paired with electric shock (50% reinforcement) with contingency reversal after 24 trials. In the social phase, participants watched videos of a demonstrator viewing colored squares, where the CS+ was followed by the demonstrator receiving a shock (50% reinforcement, with reversal). Participants reported US expectancy (yes/no) at each CS onset.
- **task_paradigm:** Fear conditioning (social)
- **players:** Single agent (participant), single target (male demonstrator in video)
- **n_players:** single agent (1)
- **partner_type:** human (recorded)
- **stimuli:** Colored squares (CS), electric shock (direct US), videos of demonstrator receiving shock (social US), binary yes/no expectancy ratings
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Robust fear learning across both phases (main effect of CS: chi-squared(1) = 26.8, p < 0.00001); no difference between direct and social phases (phase main effect: p = 0.6; CS x phase interaction: p = 0.75) - Hybrid model fit shock expectancy well (Wilcoxon V = 225, p < 0.0001); fit did not differ between phases (V = 205, p = 0.74) - Model parameters (tau and beta) did not differ between phases (tau: V = 190, p = 0.99; beta: V = 193, p = 0.67) - Conjunction CS+>CS-: left amygdala overlap (p(SVC) = 0.04, t = 2.8) - Conjunction US>noUS: bilateral amygdala (left: p(SVC) < 0.001, t = 5.35; right: p(SVC) < 0.001, t = 7.43), bilateral AI (left: p(SVC) < 0.001, t = 6.58; right: p(SVC) < 0.001, t = 5.67), dorsal ACC (p(WB-FWE) < 0.001, t = 7.95) - Conjunction associability: right AI (p(SVC) = 0.009, t = 4.25) - Amygdala associability in direct phase only (left: p(SVC) < 0.001, t = 5.78; right: p(SVC) = 0.001, t = 4.78) - Social phase: AI-TPJ connectivity stronger than direct (p(unc) < 0.001, t = 4.39) - DCM: Direct phase -- amygdala as US input (xp = best); associability gates amygdala-to-ACC (model 8, xp = 0.65). Social phase -- AI as US input; associability gates AI-to-amygdala and amygdala-to-ACC (model 10, xp = 0.42) - Empathy ratings positively linked to AI activity during social US (largest p(SVC) = 0.008, smallest t = 4.67)
- **effect_size:** No Cohen's d, r-squared, or eta-squared reported. Effect sizes are t-values and exceedance probabilities from DCM comparison. No standardized effect sizes provided for behavioral results beyond chi-squared and Wilcoxon V statistics.
- **learning_from:** Other (demonstrator); observed aversive outcome (shock to demonstrator)
- **learning_about:** World; CS-US contingency / threat value of conditioned stimuli  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** pain_threat

## Algorithmic level
- **winning_model:** Hybrid Rescorla-Wagner/Pearce-Hall model (2 free params: lambda [associability sensitivity], beta [softmax temperature])
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** Only one computational model was tested (the hybrid model). Multiple DCM models were tested for effective connectivity (19 models across two steps for each phase), but these are neuroimaging connectivity models, not computational learning models per se. - [{"name": "Hybrid RW-PH model (softmax)", "family": "Hybrid RW/PH", "n_params": 2, "metric": "AIC"}] - [{"name": "Hybrid RW-PH model (logistic)", "family": "Hybrid RW/PH", "n_params": 2, "metric": "AIC"}] (alternative response function, AIC summed: 3374 vs 3353 for softmax -- softmax selected) - DCM models: 19 models per phase tested via Bayesian model selection (exceedance probabilities)
- **model_mb_mf:** MF
- **model_params:** - lambda (0 <= lambda <= 1): free parameter determining sensitivity of stimulus-specific associability alpha to absolute prediction error on previous trial. Mean fitted value not explicitly reported in accessible text (values used for fMRI regressors were group averages but specific numbers not stated in extracted text). - beta (0 < beta <= 1): softmax temperature parameter. Mean fitted value not explicitly reported. - Q values initialized to 0.5; associability initialized to 0.5.
- **social_param:** No explicitly social parameter in the learning model. The same model with the same parameters was fit separately to direct and social phases. The social distinction emerges at the neural level (DCM), not at the computational model level.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC (for learning model); Bayesian random effects model comparison with exceedance probabilities (for DCM)
- **how_model_fit:** Individual-level fit (MLE per subject, BFGS optimization). For fMRI parametric regressors, group-average parameters were used to generate trial-by-trial regressors.
- **data_type_fit_to:** Choice behavior (binary shock expectancy ratings)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors from hybrid model: associability and prediction error as parametric modulators of US onset), PPI (generalized PPI for connectivity), DCM (dynamic causal modeling for effective connectivity)
- **contrast:** - CS+ > CS- conjunction (direct AND social): left amygdala - US > no US conjunction (direct AND social): bilateral amygdala, bilateral AI, dorsal ACC - Associability conjunction (direct AND social): right AI - Associability direct only: bilateral amygdala - Social > Direct US connectivity (gPPI from AI): right TPJ - DCM: US input and associability gating models
- **key_regions:** Shared aversive learning network: amygdala (CS+>CS- conjunction; US conjunction; associability in direct phase), anterior insula (US conjunction; associability conjunction across modalities; US input in social DCM), dorsal ACC (US conjunction; target of associability gating in both DCM phases). Social-specific: TPJ (stronger AI-TPJ coupling during social US via gPPI).
- **key_regions_abbrev:** ACC, TPJ, insula, AI, amygdala
- **coordinates_peak:** - CS+>CS- conjunction (direct & social):   - Left amygdala: -20, -2, -14 - US>noUS conjunction (direct & social):   - Left amygdala: -20, -2, -16   - Right amygdala: 28, 2, -18   - Left AI: -36, 14, -12   - Right AI: 32, 24, -2   - Dorsal ACC: 0, 28, 24 - Associability conjunction:   - Right AI: 36, 16, -10 - Associability direct phase:   - Left amygdala: -24, 0, -16   - Right amygdala: 18, -2, -14 - Associability > PE direct:   - Left amygdala: -20, -6, -14   - Right amygdala: 30, -2, -18   - Left AI: -42, -8, 6   - Right AI: 42, -8, -6 - PPI AI social > direct:   - Right TPJ: 56, -56, 38 - Supplementary Table S1 (US conjunction outside ROIs):   - Temporal Inferior gyrus L: -48, -50, 6   - Temporal Pole Mid R: 62, -36, 24   - Hippocampus L: -42, 22, -10   - Anterior Cingulate R: 0, 28, 24   - Caudate R: 4, -20, -2 - Supplementary (Associability conjunction outside ROIs):   - Temporal gyrus Mid R: 66, -42, 20   - OFC post R: 36, 16, -10   - Frontal Inf Tri R: 58, 14, 20
- **analysis_type:** Both (ROI with SVC for amygdala and AI a priori regions; whole-brain corrected for ACC and other regions; exploratory whole-brain at p < 0.001 uncorrected)  ---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 27 (28 recruited, 1 excluded for aborting experiment; 15 female; mean age = 22.8, SD = 3.33); all underwent both direct and social phases (within-subjects)
- **population_category:** healthy adults
- **population_age_range:** M=22.8
- **ecological_validity:** Low -- laboratory fear conditioning paradigm with colored squares and electric shock; social learning via pre-recorded video of a demonstrator (not live interaction); binary expectancy ratings rather than naturalistic fear responses; SCR data lost due to technical difficulties.
- **eligibility_flag:** 
- **concerns:** - Only one computational learning model tested (hybrid RW-PH); no formal model comparison against alternative learning models (e.g., pure RW, pure PH, or models with social-specific parameters) - SCR data collection failed due to technical issues -- only binary expectancy ratings available as behavioral measure - ACC ROI for DCM defined from the data (conjunction contrast), not independently -- acknowledged by authors but still a concern - Mean fitted parameter values (lambda, beta) not explicitly reported in accessible text - No prediction error signals found in conjunction -- weak evidence for PE in either phase individually - Sample size relatively small (N=27) for the complexity of the DCM analysis - DCM model space restricted by two-step approach and anatomical assumptions
- **limitations_reported:** Authors acknowledge: the study focused on three ROIs based on prior literature and found no additional social-specific regions, but other regions may contribute; overlapping macrolevel BOLD activations do not necessarily imply overlap in neuronal populations or mechanisms; the within-subjects design (experiencing both phases) may have enhanced similarity between direct and social learning relative to what would be found between subjects; perceived self-relevance of the social phase (risk of getting shocked oneself) might inflate overlap; DCM provides schematic rather than definitive account of information flow.
- **limitations_categorized:** Limited ROI coverage; reverse inference concerns; within-subjects design confound; demand characteristics / self-relevance confound; model specificity limitations; small sample size; limited ecological validity; no SCR data.
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
- **wc_rule10:** No
- **wc_score:** 3.5
- **wc_total:** 3.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM -- lambda and beta described but mean fitted values not explicitly reported in text - effect_size: LOW -- no standardized effect sizes (d, r, eta-squared) reported for behavioral comparisons; only chi-squared, Wilcoxon V, and t-values from fMRI - social_param: HIGH -- confirmed no social-specific parameter in the model
- **cannot_find:** - Mean fitted values for lambda and beta parameters (may be in figure inserts but not extractable from text) - Exact AIC values per model variant beyond summed AIC (softmax: 3353, logistic: 3374) - Individual DCM exceedance probability tables (referenced as Tables S6-S7 but formatted data was partially lost in txt conversion)
- **other_notes:** This paper tests whether direct Pavlovian and observational fear learning share computational and neural mechanisms. The key finding is that the same hybrid RW-PH model explains both, and a shared amygdala-AI-ACC network underlies both, but with different information flow: amygdala is the US input for direct learning while AI is the US input for social learning. The AI gates associability signals to ACC in both modalities. The TPJ shows stronger connectivity with AI during social learning specifically, suggesting social cognition modulates the shared aversive learning network rather than adding distinct nodes.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = parametric
- spec_locus = source
- spec_neural = dedicated
- spec_source = partly
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MB_MF_hybrid
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = threat_fear
- tax_rr_topic_threat_fear
- tax_topic_threat_fear
