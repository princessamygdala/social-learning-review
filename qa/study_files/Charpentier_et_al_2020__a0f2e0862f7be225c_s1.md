# Charpentier et al. (2020)

- **study_id:** `a0f2e0862f7be225c_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Charpentier, C. J., Iigaya, K., & O'Doherty, J. P. (2020). A neuro-computational account of arbitration between choice imitation and goal emulation during human observational learning. *Neuron*, *106*(4), 687–699.
- **citation_short:** Charpentier et al. (2020)
- **doi:** 10.1016/j.neuron.2020.02.028
- **publication_type:** peer-reviewed journal
- **year:** 2020.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** mitation’’referstoabroadrangeofcognitiveandbehav- from observation to produce posterior updated beliefs; ethreeslotmachinesisunavailable(greyedout)ineachtrial,buttheassociatedtokenprobabilities; mitationcanbedescribedinarein- influenceofthesestrategiesisdynamicallymodulateddepending; mitationinvolvesrepeatingotheragents’previousactions,whereasemulationproceedsfrominfer-; DivisionofHumanitiesandSocialSciences,CaliforniaInstituteofTechnology,Pasadena,CA,USA; mitation, individuals choose contrast,goalemulationconsistsofamorecomplexandflexible; etherlearninganewskillbyobservinganexpertperformit, e
- **code_url:** https://github.com/JoramSoch/MACS

## Computational level
- **study_focus:** Observational learning; arbitration between choice imitation and goal emulation
- **study_focus_short:** Observational learning; arbitration between choice imitation and goal emulation
- **learning_mode_description:** - Learning mode: Learning from observing another agent's choices and their associated token outcomes about the reward value of stimuli, via arbitration between imitation (copying choices) and emulation (inferring goals from token inference).   - Learning from:     - Source type (social): other (demonstrator)     - Source content (social): action/policy (choices) + outcomes (token obtained)   - Learning about:     - Target type (non-social): world (stimulus reward values)     - Target content (non-social): action/policy (which slot machine to choose) + outcome (which token is valuable)  ### 4. COMPUTATIONAL PROBLEM  How does the brain arbitrate between imitating another agent's choices and inferring that agent's goals to guide one's own decisions during observational learning? (Prediction / action-goal selection)
- **task_description:** Participants observed a demonstrator choosing between slot machines in a token-based task, where one of three tokens was secretly valuable. On play trials, participants chose for themselves; the task manipulated volatility (token switch frequency) and uncertainty (token probability distributions) to dissociate imitation from emulation strategies.
- **task_paradigm:** Observational learning task
- **players:** Single agent (participant), single social source (demonstrator — pre-recorded, described as performing optimally with full information)
- **n_players:** single agent (1)
- **partner_type:** human (recorded)
- **stimuli:** Slot machines with colored token probability distributions (green, red, blue); video of demonstrator's choices; token outcomes
- **method:** fMRI
- **method_full:** fMRI (two independent studies; Study 2 was a pre-registered replication of Study 1)
- **main_result:** - Both action learning (imitation signature) and token learning (emulation signature) significantly predicted choice: Study 1: action learning β = 0.865 ± 0.80, T₂₉ = 5.94; token learning β = 1.174 ± 1.00, T₂₉ = 6.42 (both p < 0.0001). Study 2: action β = 0.857 ± 0.60, T₂₉ = 7.78; token β = 0.843 ± 0.85, T₂₉ = 5.42 (both p < 0.0001). - Arbitration model (Model 7) had highest OOS accuracy among pre-registered models: Study 1 = 76.5%, Study 2 = 74.9%. Exploratory Model 10 (1-step imitation) outperformed: Study 1 = 76.5%, Study 2 = 76.2%. - Arbitration weight modulated by volatility (Study 1: F₁,₂₉ = 61.2; Study 2: F₁,₂₉ = 47.3) and uncertainty (Study 1: F₁,₂₉ = 267.3; Study 2: F₁,₂₉ = 124.8), all p < 0.0001. - Emulation reliability (arbitration signal): bilateral TPJ (left β = 0.201 ± 0.53, T₂₉ = 2.10; right β = 0.277 ± 0.59, T₂₉ = 2.56), right vlPFC (β = 0.250 ± 0.48, T₂₉ = 2.86), dmPFC (reliability difference β = 0.383 ± 0.89, T₂₉ = 2.37). Replicated in Study 2 for left TPJ and right vlPFC. - Chosen value: mOFC (β = 0.110 ± 0.28, T₂₉ = 2.16, positive); pre-SMA (β = −0.144 ± 0.29, T₂₉ = −2.74, negative). Replicated in Study 2. - Emulation update (KL divergence): dmPFC, pre-SMA, dorsal striatum. Replicated. - Imitation update (1-step action change): pre-SMA. Replicated. - Conjunction analysis: emulation signals overlapped with Neurosynth "mentalizing" map; imitation signals overlapped with Neurosynth "mirror" map.  ### 6. WINNING MODEL
- **effect_size:** MEDIUM — Many neural effect sizes reported as beta ± SD with T-statistics; no Cohen's d or standardized effect sizes reported for neural contrasts
- **learning_from:** 
- **learning_about:** 
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** Model 10 — Arbitration between approximate Bayesian emulation and 1-step imitation. Parameters: β_EM, β_IM, δ. 3 free parameters. Arbitration driven solely by emulation reliability (R^EM).
- **model_family:** MB/MF hybrid
- **model_class:** Other
- **all_models_tested:** 
- **model_mb_mf:** MB/MF hybrid (emulation = MB-like goal inference; imitation = MF-like action copying)  ### 7. ALL MODELS TESTED  | # | Name | Family | n_params | Metric | |---|------|--------|----------|--------| | 1 | Emulation inference (fixed λ) | Bayesian inference | 1 (β) | OOS accuracy, iBIC | | 2 | Emulation inference (free λ) | Bayesian inference | 2 (β, λ) | OOS accuracy, iBIC | | 3 | Imitation RL (fixed α) | RL | 2 (β, α) | OOS accuracy, iBIC | | 4 | Imitation RL (dynamic α) | RL (Pearce-Hall) | 3 (β, η, α₀) | OOS accuracy, iBIC | | 5 | Emulation RL (fixed α) | RL | 2 (β, α) | OOS accuracy, iBIC | | 6 | Emulation RL (dynamic α) | RL (Pearce-Hall) | 3 (β, η, α₀) | OOS accuracy, iBIC | | 7 | Arbitration (fixed λ) | Hybrid (Bayesian + RL) | 4 (β_EM, β_IM, δ, α) | OOS accuracy, iBIC | | 8 | Arbitration (free λ) | Hybrid (Bayesian + RL) | 5 (β_EM, β_IM, δ, α, λ) | OOS accuracy, iBIC | | 9 | Outcome RL | RL | 2 (β, α) | OOS accuracy, iBIC | | 10 | Arbitration with 1-step IM (exploratory) | Hybrid (Bayesian + 1-step) | 3 (β_EM, β_IM, δ) | OOS accuracy, iBIC |  ### 8. MODEL COMPARISON, FIT, DATA TYPE
- **model_params:** 
- **social_param:** 
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Out-of-sample predictive accuracy (5-fold cross-validation) + group-level integrated Bayesian information criteria (iBIC) via hierarchical Bayesian random effects (EM with Laplace approximation)
- **how_model_fit:** Individual-level fit (MLE via fminunc) + hierarchical Bayesian group-level
- **data_type_fit_to:** Choice behavior  ### 9. NEUROIMAGING DETAILS

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors) + Bayesian model selection between GLMs
- **contrast:** - Emulation reliability (arbitration signal): bilateral TPJ, right vlPFC, ACC, bilateral insula (conjunction)   - Emulation update (token KL divergence at feedback): dmPFC, pre-SMA, dorsal striatum, bilateral anterior insula, bilateral IFG   - Imitation update (action change at feedback): pre-SMA, bilateral IPL, left dlPFC   - Chosen value at play: mOFC (+), pre-SMA (−)   - Reliability difference (EM − IM): dmPFC, left TPJ, ACC, right anterior insula, right IFG
- **key_regions:** Emulation reliability tracked in bilateral TPJ and right vlPFC as arbitration signal; emulation learning update (KL divergence) in dmPFC, pre-SMA, dorsal striatum; imitation update (1-step action change) in pre-SMA and bilateral IPL; chosen value in mOFC; arbitration overlaps with vlPFC region also found in MB/MF arbitration (Lee et al., 2014).  ### 10. COORDINATES (PEAK MNI, from Tables S2 and S4)
- **key_regions_abbrev:** dStr, striatum, mPFC, dmPFC, OFC, TPJ
- **coordinates_peak:** Pre-registered ROI-based (Table S1)**: - Left TPJ/pSTS: −54, −53, 22 (approximate centroid from pre-registered ROI) - Right TPJ/pSTS: 58, −58, 20 (approximate) - mOFC: ROI-based (no single peak reported for ROI) - dmPFC: ROI-based - Pre-SMA/dACC: ROI-based - Left vlPFC: ROI-based - Right vlPFC: ROI-based - Dorsal striatum: ROI-based  **Whole-brain clusters, Study 1 (Table S2)**: - Emulation reliability: R anterior insula: 43, 17, −12 - Imitation reliability: mOFC/vmPFC/ACC: 3, 37, −7 - Imitation reliability (negative): R inferior parietal/angular gyrus: 48, −46, 58 - Imitation action value diff: R dlPFC: 30, 24, 41; R TPJ: 48, −49, 36; pre-SMA/dmPFC: −5, 24, 53; L dlPFC: −43, 19, 41; precuneus: 3, −61, 18; L thalamus: −15, −29, 11; L TPJ: −48, −59, 36 - Token entropy: Bilateral IPL/angular/TPJ/precuneus: 38, −49, 46; R dlPFC/IFG/OFC/vlPFC: 28, 9, 61; L dlPFC/IFG/OFC/vlPFC: −20, −4, 63; dmPFC/pre-SMA/dACC: −8, 29, 41 - Token KL divergence: L anterior insula: −33, 14, −10; R IFG/precentral: 35, 9, 33; R anterior insula: 40, 19, −2; pre-SMA/dACC: −8, 19, 46; L IFG/precentral: −48, 7, 26; R supramarginal/IPL: 53, −39, 46 - Reliability difference (EM−IM): R anterior insula: 40, 17, −12; R IFG: 45, 4, 21; ACC/dmPFC: 13, 44, 26; R angular gyrus: 40, −74, 48  **Conjunction Study 1 × Study 2 (Table S4)**: - Arbitration (emulation reliability): ACC: 0, 39, 3; R vlPFC/insula: 53, 32, 1; L pSTS/TPJ: −58, −54, 13; dACC: 5, 17, 31 - Emulation update (token KL divergence): L anterior insula: −35, 17, −7; R anterior insula: 35, 19, −10; R IFG: 43, 9, 26; L IFG: −40, 7, 28; R caudate/thalamus: 8, −1, 8; SMA/pre-SMA: 5, 22, 48; R TPJ/pSTS: 55, −44, 23 - Imitation update (action change): SMA/pre-SMA: −5, 4, 66; L IPL: −38, −54, 41; R IPL: 50, −39, 48; L dlPFC: −45, 32, 31; L anterior insula: −35, 22, −10  - **Analysis type**: Both (pre-registered ROI + whole-brain with cluster-level FWE correction)
- **analysis_type:** Both (pre-registered ROI + whole-brain with cluster-level FWE correction)
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** - Study 1: N = 30 (12 female, 18 male; mean age 31.67 ± 4.94) - Study 2: N = 30 (12 female, 18 male; mean age 31.2 ± 8.15; 3 excluded from original 33) - Total: N = 60 fMRI
- **population_category:** healthy adults
- **population_age_range:** M=31.67
- **ecological_validity:** Lab-based observational learning task with pre-recorded demonstrator and abstract slot machine stimuli. Good experimental control and clean dissociation of strategies, but limited ecological validity — no real social interaction, no face-to-face observation, abstract rather than naturalistic stimuli. The demonstrator is described as always performing optimally, which is unrealistic.  ### 13. ELIGIBILITY FLAG  null (fully eligible: computational modeling, human behavioral data, learning in a social context over time)  ### 14. CONCERNS & LIMITATIONS
- **eligibility_flag:** 
- **concerns:** The "demonstrator" is pre-recorded and always optimal — no genuine social interaction. The exploratory Model 10 was not pre-registered and its superiority over Model 7 should be interpreted with caution, though it was tested on both independent datasets. Two studies but from same lab/paradigm.
- **limitations_reported:** - Future optimizations of the task design could make the two strategies more distinguishable by increasing the proportion of trials in which behavior is consistent with one strategy but not the other; - The imitation framework is applied to decision-making and does not address the operationalization of imitation in which specific motor actions are reproduced; - Emulation in this task involves inferring which of three possible goals is pursued — other implementations focus on different types of social inference (inverse RL, trust learning, recursive belief inference); - Open questions remain about how specific implementations of imitation or emulation differ mechanistically, how adaptable the arbitration framework is, and whether it can be generalized to complex real-world learning situations; - Functional connectivity analyses needed to understand how arbitration is implemented at the network level; - Brain stimulation methods needed to establish causal effects
- **limitations_categorized:** Task simplicity; limited ecological validity; limited generalizability (specific operationalizations of imitation/emulation); no causal inference (correlational fMRI only); no functional/effective connectivity analysis  ### 15. WILSON & COLLINS CHECKLIST  1. **Design a good experiment**: Yes — task designed to dissociate imitation and emulation via slot machine/token structure with volatility × uncertainty manipulation 2. **Design good models**: Yes — 10 models across 5 classes tested (emulation-only, imitation-only, emulation-RL, arbitration, outcome-RL) 3. **Simulate, simulate, simulate**: Yes — simulations described (practice trial simulations for min/max normalization; model-generated data used for posterior predictive checks) 4. **Fit the parameters**: Yes — MLE (fminunc) + hierarchical Bayesian EM with Laplace approximation 5. **Check parameter recovery**: Yes — implied by cross-validation and replication design; posterior predictive analysis confirms model generates expected behavioral signatures (Figures 2C, 2D) 6. **Check model recovery**: Yes — model specificity demonstrated: emulation-only model recovers only token learning, imitation-only recovers only action learning, arbitration model recovers both (Figures 2C, 2D). Not a formal confusion matrix but functionally equivalent. 7. **Fit real data and compare models**: Yes — 10 models compared via OOS accuracy and iBIC 8. **Validate the winning model**: Yes — posterior predictive checks showing winning model generates both behavioral signatures; model validated across two independent samples 9. **Analyze the winning model**: Yes — extracted arbitration weights, examined modulation by volatility/uncertainty, individual differences in bias parameter correlated with neural signals 10. **Report results transparently**: Yes — behavioral data on OSF (https://osf.io/49ws3/), fMRI T-maps on NeuroVault, custom code on GitHub (https://github.com/ccharpen/ObsLearn_arbitration), pre-registration on OSF (https://osf.io/37xyq)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 10
- **wc_total:** 10.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
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
- rr_tax_mod_action_observation
- rr_tax_mod_mentalizing_inference
- spec_depth = structural
- spec_locus = source+target
- spec_neural = dedicated
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_mod_mentalizing_inference
- tax_model_MB
- tax_model_MB_MF_hybrid
- tax_model_bayesian
- tax_param_MB_MF_balance
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_MB_MF_hybrid
- tax_rr_model_family = MB_MF_hybrid
- tax_rr_param_MB_MF_balance
- tax_rr_param_precision
- tax_rr_primary_topic = imitation_emulation
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_imitation_emulation
- tax_rr_topic_mentalizing
- tax_topic_imitation_emulation
- tax_topic_mentalizing
