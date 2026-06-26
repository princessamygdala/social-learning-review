# Gu et al. (2015)

- **study_id:** `aeb52cfb7ce319e37_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Gu, X., Wang, X., Hula, A., Wang, S., Xu, S., Lohrenz, T. M., Knight, R. T., Gao, Z., Dayan, P., & Montague, P. R. (2015). Necessary, yet dissociable contributions of the insular and ventromedial prefrontal cortices to norm adaptation: Computational and lesion evidence in humans. *The Journal of Neuroscience*, *35*(2), 467–473. https://doi.org/10.1523/JNEUROSCI.2906-14.2015
- **citation_short:** Gu et al. (2015)
- **doi:** 10.1523/JNEUROSCI.2906-14.2015
- **publication_type:** peer-reviewed journal
- **year:** 2015.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** UniversityofCalifornia,Berkeley,California94720,7GatsbyComputationalNeuroscienceUnit,UniversityCollegeLondon,London,UnitedKingdom; ethreecomputationalsignalsofinterestasparticipantsplayedafairnessgame(ultimatumgame):sensitivitytothefairnessofoffers,; Institute,Roanoke,Virginia24016,3DepartmentofNeurosurgery,BeijingTiantanHospital,CapitalMedicalUniversity,and4China; CentreforNeuroimaging,UniversityCollegeLondon,London,UnitedKingdomWC1N3BG,2HumanNeuroimagingLaboratory,Virginia; CenterforNeurologicalDiseases,Beijing,China100050,5HelenWillisNeuroscienceInstituteand6DepartmentofPsychology,; Departm
- **code_url:** 

## Computational level
- **study_focus:** Norm learning / norm adaptation — dissociable roles of insula (norm adaptation rate) and vmPFC (fairness valuation) during social exchange.
- **study_focus_short:** Norm learning / norm adaptation
- **learning_mode_description:** - Learning mode: Learning from offers in a fairness game about evolving social norms   - Learning from:     - Source type (social): other (virtual proposer)     - Source content (non-social): outcome (monetary offer split)   - Learning about:     - Target type (social): social structure (prevailing fairness norm)     - Target content (social): state (mental state; expected norm of fairness)
- **task_description:** Participants played the responder role in a one-shot ultimatum game over 45 rounds, each with a different virtual proposer offering a split of ¥20 Chinese Yuan. Participants decided to accept or reject each offer.
- **task_paradigm:** Ultimatum game
- **players:** Single agent (participant as responder), multi-target (45 different virtual proposers, one per round)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Monetary offer splits (¥1–¥10 of ¥20), text-based proposals with proposer name
- **method:** lesion / behavioural
- **method_full:** behavioural (lesion study)
- **main_result:** - Patients with insula lesions showed abnormally low norm adaptation rate ε compared to controls (bootstrapping p < 0.05) - Patients with insula lesions showed increased sensitivity to norm prediction error α compared to controls (p < 0.05) - Patients with vmPFC lesions showed reduced sensitivity to fairness (logistic β₁ coefficient; p < 0.01) - Patients with vmPFC lesions showed lower initial norm f₀ than controls (p < 0.01) - Patients with vmPFC lesions showed higher adaptation rate ε than controls (p < 0.05)
- **effect_size:** Only bootstrapped p-values reported; no standardized effect sizes (Cohen's d, r, etc.) provided in the paper. Flag: effect sizes not reported in standard format.
- **learning_from:** Other (virtual proposer); monetary offer outcomes in fairness game
- **learning_about:** Social norms (internal representation of expected fair offer / fairness norm)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** RW with variable initial norm (3 params: ε norm adaptation rate, α sensitivity to norm PE, β softmax inverse temperature, f₀ initial norm) - Note: The paper describes 3 key parameters (ε, α, β) plus f₀ as a fitted initial condition, totaling 4 free parameters.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "RW variable initial norm", "family": "Rescorla-Wagner", "n_params": 4, "metric": "BIC (modified for small samples)"} 2. {"name": "RW fixed initial norm (f₀=10)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "BIC"} 3. {"name": "Fehr-Schmidt (non-learning)", "family": "Utility function", "n_params": 2, "metric": "BIC"} 4. {"name": "Bayesian variable initial", "family": "Bayesian belief updating", "n_params": 4, "metric": "BIC"} 5. {"name": "Bayesian fixed initial", "family": "Bayesian belief updating", "n_params": 3, "metric": "BIC"}
- **model_mb_mf:** MF
- **model_params:** - ε (norm adaptation rate) [S]: determines how quickly internal norm updates based on preceding offer. Range [0,1]. Insula patients: significantly lower than controls. vmPFC patients: significantly higher than controls. Mean fitted values not reported numerically (only shown in figures). - α (sensitivity to norm prediction error / "envy") [S]: sensitivity to deviation of offer from internal norm. Range [0,1]. Insula patients: significantly higher than controls. Mean fitted values not reported numerically. - β (softmax inverse temperature): governs choice stochasticity. Range [0,1]. No significant group differences. - f₀ (initial internal norm): fitted individually, range [0,20]. vmPFC patients: significantly lower than controls.
- **social_param:** ε (norm adaptation rate) — speed at which internal social norm adjusts to observed offers; α (sensitivity to norm prediction error) — sensitivity to deviations between offers and the expected social norm.
- **social_param_name:** ε
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 0–1
- **model_comparison_metric:** Modified BIC (Bayesian Information Criterion) for small samples (Haughton, 1988), normalized based on sample size. Lowest BIC = highest model evidence.
- **how_model_fit:** individual-level-fit (parameters estimated individually per subject, with multiple starting points to avoid local minima)
- **data_type_fit_to:** choice behavior (binary accept/reject decisions)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (lesion study, no fMRI)
- **contrast:** N/A — lesion study comparing patient groups (insula, vmPFC, BDC) vs. neurologically intact controls on model parameters using bootstrapping.
- **key_regions:** Insula lesions disrupted norm adaptation rate (learning); vmPFC lesions reduced fairness sensitivity and initial norm. Dissociable causal roles: insula necessary for norm learning, vmPFC necessary for fairness valuation.
- **key_regions_abbrev:** vmPFC, mPFC, insula, AI
- **coordinates_peak:** unavailable — lesion study, no activation coordinates reported. Lesion locations shown as overlap maps in MNI space (Fig. 1A: insula, centered around x=-38; Fig. 1B: vmPFC, centered around x=-2), but no peak activation coordinates.
- **analysis_type:** N/A (no neuroimaging analysis; lesion-behavior mapping)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** N=59 total (40 neurologically intact controls [21F/19M], 7 insula lesion patients [4F/3M], 6 vmPFC lesion patients [3F/3M], 6 brain-damaged controls [2F/4M]). Ages: NC 48±12, BDC 42±11, Insula 42±8, vmPFC 54±13.
- **population_category:** clinical
- **population_age_range:** 
- **ecological_validity:** Low — participants responded to virtual (not real) proposers in a one-shot ultimatum game; no face-to-face social interaction; offers were pre-determined, not generated by real partners. However, the use of lesion patients provides causal evidence not available from fMRI alone.
- **eligibility_flag:** 
- **concerns:** - Very small patient group sizes (n=7 insula, n=6 vmPFC) limit statistical power and generalizability. - The RW variable initial norm model was the winning model overall and for NC, BDC, and insula groups individually, but NOT for vmPFC patients — the authors note vmPFC parameters should be interpreted with caution. - No standardized effect sizes reported; only bootstrapped p-values. - Mean fitted parameter values are displayed in figures only, not reported numerically in text or tables. - Supplemental materials hosted externally (Google Sites) and not available in the papers folder; Supplemental Table 1 reportedly contains parameter estimates for all five models but could not be accessed. This may mean exact mean parameter values exist but are inaccessible. - Virtual proposers reduce ecological validity compared to real social interaction.
- **limitations_reported:** One limitation of our study is that we did not directly measure subjective feelings or related physiological responses"; "Future studies are needed to better understand whether the learning deficits observed in insula patients arise purely from a lack of physiological/feeling signals that are normally provided by the insula, or rather, also higher-level abnormalities in associating bodily responses with value and prediction error signals"; "Future studies are needed to assess whether insula lesion-related social and nonsocial learning deficits directly correlate with each other.
- **limitations_categorized:** No physiological measures collected; unclear mechanism (interoception vs. higher-level computation); limited generalizability (social vs. nonsocial learning deficits not compared); small sample size
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
- **wc_rule10:** Partial
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - effect_size: LOW — no standardized effect sizes reported, only bootstrapped p-values - model_params (mean fitted values): MEDIUM — values shown in figures but not reported numerically in text; supplement reportedly contains Table 1 with all parameter estimates but supplement not accessible - winning_model n_params: MEDIUM — paper describes ε, α, β as 3 parameters plus f₀ as a fourth fitted value; counted as 4 total free parameters - wc_guidelines rule 3: MEDIUM — supplemental figure shows simulations but unclear if done before fitting to real data - learning_mode source_type: MEDIUM — proposers are virtual (automated), classified as social because they represent social agents in the task framing
- **cannot_find:** - Exact mean fitted parameter values for each group (reportedly in Supplemental Table 1, which is hosted externally and not accessible) - Supplemental analysis details (random effects RW model mentioned in Notes section) - Standardized effect sizes - Code or data availability statement
- **other_notes:** - Supplemental materials hosted at external Google Sites URL (https://sites.google.com/site/xgufmri/download) — not peer reviewed per the paper's own statement. Supplement not available in the papers folder. This limits extraction completeness for parameter values and additional model details. - The paper is a Brief Communication (7 pages), which constrains the level of methodological detail provided. - The "virtual proposer" design means the social agent is automated — flagged per CLAUDE.md instructions but paper remains eligible. - The Bayesian observer model is an interesting alternative that was tested but did not win; it uses conjugate Normal-Inverse-Chi-squared updating of mean and variance of offer distribution.
- **re_extract_flag:** false (full text accessible; however, supplement not accessible — parameter values from Supplemental Table 1 could improve extraction if obtained)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = shared
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = norm_conformity
- tax_rr_secondary_topic = fairness_inequity
- tax_rr_topic_fairness_inequity
- tax_rr_topic_norm_conformity
- tax_topic_fairness_inequity
- tax_topic_norm_conformity
