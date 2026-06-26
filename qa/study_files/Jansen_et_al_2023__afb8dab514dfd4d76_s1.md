# Jansen et al. (2023)

- **study_id:** `afb8dab514dfd4d76_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Jansen, M., Lockwood, P. L., Cutler, J., & de Bruijn, E. R. A. (2023). l-DOPA and oxytocin influence the neurocomputational mechanisms of self-benefitting and prosocial reinforcement learning. *NeuroImage*, *270*, 119983. https://doi.org/10.1016/j.neuroimage.2023.119983
- **citation_short:** Jansen et al. (2023)
- **doi:** 10.1016/j.neuroimage.2023.119983
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** ether with the learning rate, which quantifies are associated with reward processing, such as the ventral striatum (VS); Department of Clinical Psychology, Leiden University, Wassenaarseweg 52, 2333 AK Leiden, the Netherlands; ether pharmacological manipulation of oxytocin and dopamine influence the neurocomputational mechanisms; Centre for Human Brain Health, School of Psychology, University of Birmingham, Birmingham, UK; Institute for Mental Health, School of Psychology, University of Birmingham, Birmingham, UK; Centre for Developmental Science, School of Psychology, University of Birmingham
- **code_url:** 

## Computational level
- **study_focus:** Prosocial learning; pharmacological modulation of self-benefitting versus prosocial reinforcement learning by dopamine (l-DOPA) and oxytocin
- **study_focus_short:** Prosocial learning
- **learning_mode_description:** - Learning mode: Learning from reward outcomes about stimulus-reward associations for self and others   - Learning from:     - Source type (non-social): self (own choices)     - Source content (non-social): outcome (monetary reward/no reward for chosen symbol)   - Learning about:     - Target type (social): other (anonymous other participant) [in prosocial condition]     - Target type (non-social): self [in self-benefitting condition]; world [in no-one control condition]     - Target content (non-social): stimulus (stimulus-reward probability associations)
- **task_description:** In a probabilistic reinforcement learning task, participants chose between two abstract symbols (75% vs 25% reward probability) to earn points converted to money for themselves (self), an anonymous other participant (prosocial), or no one (control), across three pharmacological sessions (l-DOPA, oxytocin, placebo) in a double-blind crossover design. Participants performed 3 blocks of 16 trials per recipient condition (144 trials per session) while undergoing fMRI.
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), single anonymous other (recipient in prosocial condition); N=30 healthy males
- **n_players:** network (5+)
- **partner_type:** unclear
- **stimuli:** Abstract symbols (pairs), binary feedback (100 vs 0 points), text indicating recipient ("you / other / no one")
- **method:** fMRI / pharmacological
- **method_full:** fMRI (pharmacological: l-DOPA, oxytocin, placebo cross-over)
- **main_result:** - Main Results:   - Behavior best explained by 3alpha-1beta model (exceedance probability = 0.62; iBIC = 10,713; R^2 = 0.724)   - Learning rates higher for Other vs Self (b = 0.0038, SE = 0.0010, t = 3.69, BF10 = 42.3)   - Learning rates higher for Other vs No one (b = 0.0104, SE = 0.0037, t = 2.80, BF10 = 11.3)   - No significant drug effects on learning rates or beta parameters (BF10 l-DOPA = 0.186; BF10 OT = 0.179)   - Both l-DOPA and OT blunted positive PE signaling in VS (l-DOPA: left VS, Z = 3.66, P = 0.020 SVC-FWE; OT: bilateral VS clusters, all Ps < 0.043 SVC-FWE)   - Both drugs induced negative PE signaling in aMCC, dlPFC, IPG, precentral gyrus (all P < 0.05 FWE whole-brain)   - OT x Recipient interaction: opposing self vs prosocial PE signaling in dACC (Z = 4.90, P = 0.011 FWE), insula (Z = 4.76, P = 0.019 FWE), STG (Z = 6.16, P < 0.001 FWE)   - After OT, prosocial PE signals in dACC correlated with prosocial learning rate (r = 0.507, P = 0.006)   - After OT, prosocial PE signals in insula correlated with prosocial learning rate (r = 0.537, P = 0.003)   - After OT, prosocial PE signals in STG correlated with prosocial learning rate (r = 0.547, P = 0.003)
- **effect_size:** - Main Results:   - Behavior best explained by 3alpha-1beta model (exceedance probability = 0.62; iBIC = 10,713; R^2 = 0.724)   - Learning rates higher for Other vs Self (b = 0.0038, SE = 0.0010, t = 3.69, BF10 = 42.3)   - Learning rates higher for Other vs No one (b = 0.0104, SE = 0.0037, t = 2.80, BF10 = 11.3)   - No significant drug effects on learning rates or beta parameters (BF10 l-DOPA = 0.186; BF10 OT = 0.179)   - Both l-DOPA and OT blunted positive PE signaling in VS (l-DOPA: left VS, Z = 3.66, P = 0.020 SVC-FWE; OT: bilateral VS clusters, all Ps < 0.043 SVC-FWE)   - Both drugs induced negative PE signaling in aMCC, dlPFC, IPG, precentral gyrus (all P < 0.05 FWE whole-brain)   - OT x Recipient interaction: opposing self vs prosocial PE signaling in dACC (Z = 4.90, P = 0.011 FWE), insula (Z = 4.76, P = 0.019 FWE), STG (Z = 6.16, P < 0.001 FWE)   - After OT, prosocial PE signals in dACC correlated with prosocial learning rate (r = 0.507, P = 0.006)   - After OT, prosocial PE signals in insula correlated with prosocial learning rate (r = 0.537, P = 0.003)   - After OT, prosocial PE signals in STG correlated with prosocial learning rate (r = 0.547, P = 0.003)
- **learning_from:** Self; own reward outcomes (100 vs 0 points) on chosen abstract symbol
- **learning_about:** Stimulus-reward probability associations; outcomes benefit self, other (anonymous participant), or no one  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Rescorla-Wagner (3 alpha, 1 beta: alpha_self, alpha_other, alpha_no_one; 1 beta)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "1alpha-1beta", "family": "Rescorla-Wagner", "n_params": 2, "metric": "iBIC=10837, R2=0.701, EP=0.38"} - {"name": "3alpha-1beta", "family": "Rescorla-Wagner", "n_params": 4, "metric": "iBIC=10713, R2=0.724, EP=0.62"} - {"name": "2alpha-1beta (self vs not-self)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "iBIC=10820, R2=0.713, EP=0.00"} - {"name": "3alpha-3beta", "family": "Rescorla-Wagner", "n_params": 6, "metric": "iBIC=10960, R2=0.721, EP=0.00"}
- **model_mb_mf:** MF
- **model_params:** MEDIUM confidence — mean fitted parameter values for learning rates not reported numerically in text (shown only in figures); beta values also not reported numerically
- **social_param:** alpha_other — learning rate specific to learning when outcomes benefit an anonymous other person; alpha_self — learning rate for self-benefitting learning. The recipient-specific learning rates capture how quickly participants update stimulus values depending on who benefits.
- **social_param_name:** alpha_other
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** iBIC (integrated Bayesian Information Criterion), exceedance probability (random-effects BMS via SPM12 spm_BMS), choice probability R^2
- **how_model_fit:** Individual-level fit using iterative MAP (maximum a posteriori) estimation: first MLE, then MAP with group-level Gaussian priors, iterated until convergence (change in posterior likelihood < 0.001 or max 800 steps). Fitted across drug sessions (pooled).
- **data_type_fit_to:** Choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors: PE at outcome, expected value at cue)
- **contrast:** - Placebo > l-DOPA: PE signaling (main effect of drug, domain-general) - Placebo > OT: PE signaling (main effect of drug, domain-general) - Conjunction [Placebo > l-DOPA] = [Placebo > OT]: overlap in drug effects on PE - OT x Recipient interaction: Placebo:Self[1]-Other[-1], OT:Self[-1]-Other[1] (opposing self vs prosocial PE signaling) - l-DOPA x Recipient interaction in SPG - ROI analyses in VS, sgACC, midbrain
- **key_regions:** Both l-DOPA and OT blunted positive PE signaling in VS; both drugs induced negative PE signaling in aMCC/(pre-)SMA, dlPFC, IPG, precentral gyrus; OT specifically induced opposing self vs prosocial PE signaling in dACC, insula, and STG; sgACC showed Self > Other PE under placebo only; no midbrain effects observed.
- **key_regions_abbrev:** dlPFC, dACC, ACC, sgACC, insula, AI, midbrain
- **coordinates_peak:** MEDIUM confidence — full coordinate tables are in Table S4 of supplement, but the table was extracted as text headers only (column labels visible but coordinate rows may not have fully extracted from PDF). Key peaks from main text are reported above. Note: "reported in Table S4" for some whole-brain peaks because the supplement text extraction did not include the full tabular data.
- **analysis_type:** Both (ROI + whole-brain)  ---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** N = 30 (healthy right-handed males, ages 18-35, M = 22.8, SD = 3.6); N = 28 for fMRI analyses (2 excluded for excessive motion; 2 additional participants had one session excluded each)
- **population_category:** healthy adults
- **population_age_range:** 18–35
- **ecological_validity:** Low-moderate. Task uses abstract symbols and binary monetary feedback in scanner; prosocial condition involves anonymous other with no reciprocity or personal cost; no face-to-face interaction; confederate not present. Data collected during COVID pandemic, which authors note may have increased prosocial motivation. Male-only sample limits generalizability.
- **eligibility_flag:** 
- **concerns:** - Male-only sample limits generalizability to females - Ceiling effects in task performance may have masked behavioral drug effects - No significant behavioral effects of drugs despite neural effects (neural-behavioral dissociation complicates interpretation) - Task relatively easy (participants acknowledge this in subjective reports) - COVID pandemic context may have altered baseline prosocial motivation - Parameter recovery relies on prior study (Cutler et al., 2021) rather than being fully demonstrated in this specific sample/drug context - No preregistration reported - Cannot disentangle whether negative PE signaling reflects inverse tracking of positive outcomes vs enhanced tracking of negative outcomes
- **limitations_reported:** Current study focused on one specific type of prosocial setting with no personal cost; learning took place in private context; played for anonymous peer only, not close others; male-only sample; ceiling effects possible given high accuracy; lack of behavioral drug effects may reflect insufficient sensitivity of learning paradigm; healthy adults may already show optimal DA levels limiting further enhancement; task design cannot disentangle whether negative PE signaling reflects inverse tracking of better-than-expected outcomes or increased tracking of worse-than-expected outcomes; OT effects may be dose-dependent; cultural differences with previous UK-based studies
- **limitations_categorized:** Limited ecological validity; sample homogeneity (male-only); ceiling effects; limited generalizability (single prosocial scenario); task simplicity; neural-behavioral dissociation; dose-response uncertainty; cultural specificity
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** Partial
- **wc_rule6:** Partial
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 8.0
- **wc_total:** 8.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pharma_dopamine
- pharma_oxytocin
- pop_healthy_adults
- rr_pharma_dopamine
- rr_pharma_oxytocin
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = target
- spec_neural = dedicated
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_popclass_healthy
- tax_popclass_pharmacological
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_topic_prosocial_altruism
- tax_social_nonsocial_comparison
- tax_topic_prosocial_altruism
