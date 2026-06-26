# Story et al. (2024)

- **study_id:** `ab9bdfac589e098a5_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Story, G. W., Smith, R., Moutoussis, M., Berwian, I. M., Nolte, T., Bilek, E., Siegel, J. Z., & Dolan, R. J. (2024). A social inference model of idealization and devaluation. *Psychological Review*, *131*(3), 749--780. https://doi.org/10.1037/rev0000430
- **citation_short:** Story et al. (2024)
- **doi:** 10.1037/rev0000430
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** Centre for Neuroimaging is supported by core funding from the OpenAccessfundingprovidedbyUniversityCollegeLondon:Thiswork; UniversityCollege LondonCentreforComputational PsychiatryandAgeingResearch,UniversityCollege London; mpiricaldata,tomeasureindividualsusceptibilitytorelationalinstability; InstituteforBrainResearch,Tulsa,Oklahoma,UnitedStates; CentreforChildren andFamilies, London,United Kingdom; CentreforHumanNeuroimaging,UniversityCollege London; University College London Centre for Computational; InstituteforHealthResearch,andtheMaxPlanckSociety; emails: g.story@ucl.ac.uk
- **code_url:** 

## Computational level
- **study_focus:** Trait inference / moral impression formation -- splitting (dichotomous thinking), idealization and devaluation of others' moral character, with application to borderline personality disorder (BPD).
- **study_focus_short:** Trait inference / moral impression formation -- splitting (dichotomous
- **learning_mode_description:** - Learning mode: Learning from observed moral choices of another agent about that agent's moral character (disposition), while attributing counter-evidence to external situational factors.   - Learning from:     - Source type (social): other (observed agent / "Decider")     - Source content (social): action/policy (moral choices -- acceptance of money in exchange for shocks to a third party)   - Learning about:     - Target type (social): other (observed agent)     - Target content (social): state (mental state; moral disposition / harm aversion trait)
- **task_description:** Participants observed choices made by two simulated agents ("Deciders") who selected between options involving money for themselves and electric shocks for a third party. After each prediction and every three observations, participants rated each agent's moral character and their uncertainty about that impression.
- **task_paradigm:** Impression formation task
- **players:** Single agent (participant), multi-target (2 simulated agents: 1 "bad," 1 "good")
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Binary choice options (money vs. shocks trade-offs), text-based feedback (correct/incorrect predictions), moral character rating scales (0--100)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Split-HMM (Model 3: Bad + Integrated + Good priors) outperformed Integrated-only model (mean $\Delta$BIC = 18.0; mean log LR = 12.5; $\chi^2$(2) = 25.0, p < .0001)   - Split-HMM outperformed split-only model (mean $\Delta$BIC = 135; mean log LR = 71.1; $\chi^2$(2) = 142.1, p < .0001)   - Split-HMM outperformed HGF model in accounting for moral character ratings (total $\Delta$BIC = 1827, mean $\Delta$BIC = 12.6)   - McFadden's pseudo-$R^2$ = 0.22 for best-fitting Split-HMM   - $\psi_{Bad}$ significantly greater in BPD than non-BPD (t(120) = 2.14, p = .034)   - $\psi_{Split}$ significantly greater in BPD than non-BPD (t(120) = 2.34, p = .021)   - Non-BPD $\psi_{Bad}$ significantly < 0.5 (mean = 0.30, t(101) = -6.10, p < .0001), indicating positive bias   - BPD $\psi_{Bad}$ not different from 0.5 (mean = 0.47, t(101) = -0.40, p = .69), indicating symmetric splitting   - KS test: prior ratings differ between BPD and non-BPD (p = .038, KS = 0.24)   - Agent x Group interaction on learning rate: t(241) = -3.59, p = .0004   - Main effect of agent on learning rate: t(241) = 11.8, p < .0001   - Parameter recovery: Pearson r = 0.64 ($\psi_{Bad}$) and 0.74 ($\psi_{Split}$)
- **effect_size:** - Main Results:   - Split-HMM (Model 3: Bad + Integrated + Good priors) outperformed Integrated-only model (mean $\Delta$BIC = 18.0; mean log LR = 12.5; $\chi^2$(2) = 25.0, p < .0001)   - Split-HMM outperformed split-only model (mean $\Delta$BIC = 135; mean log LR = 71.1; $\chi^2$(2) = 142.1, p < .0001)   - Split-HMM outperformed HGF model in accounting for moral character ratings (total $\Delta$BIC = 1827, mean $\Delta$BIC = 12.6)   - McFadden's pseudo-$R^2$ = 0.22 for best-fitting Split-HMM   - $\psi_{Bad}$ significantly greater in BPD than non-BPD (t(120) = 2.14, p = .034)   - $\psi_{Split}$ significantly greater in BPD than non-BPD (t(120) = 2.34, p = .021)   - Non-BPD $\psi_{Bad}$ significantly < 0.5 (mean = 0.30, t(101) = -6.10, p < .0001), indicating positive bias   - BPD $\psi_{Bad}$ not different from 0.5 (mean = 0.47, t(101) = -0.40, p = .69), indicating symmetric splitting   - KS test: prior ratings differ between BPD and non-BPD (p = .038, KS = 0.24)   - Agent x Group interaction on learning rate: t(241) = -3.59, p = .0004   - Main effect of agent on learning rate: t(241) = 11.8, p < .0001   - Parameter recovery: Pearson r = 0.64 ($\psi_{Bad}$) and 0.74 ($\psi_{Split}$)
- **learning_from:** Other's moral choices (observed agent's decisions between money and shocks)
- **learning_about:** Other's moral disposition / harm aversion (character trait)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Split-HMM (hierarchical hidden Markov model with Bad, Integrated, and Good dispositional priors; 5 free params: $\pi_{o1}$, $\pi_{s1}$, $\psi_{Bad}$, $\psi_{Split}$, $\psi_{Ext}$)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** - {"name": "Split-HMM Model 1 (Integrated only)", "family": "Hierarchical HMM", "n_params": 3, "metric": "BIC, LRT"} - {"name": "Split-HMM Model 2 (Bad + Good only)", "family": "Hierarchical HMM", "n_params": 3, "metric": "BIC, LRT"} - {"name": "Split-HMM Model 3 (Bad + Integrated + Good)", "family": "Hierarchical HMM", "n_params": 5, "metric": "BIC, LRT"} - {"name": "HGF (Hierarchical Gaussian Filter)", "family": "HGF / Bayesian continuous", "n_params": 4, "metric": "BIC, LRT"}
- **model_mb_mf:** Bayesian
- **model_params:** - $\pi_{o1}$: Likelihood precision for behavior (first-level); free parameter - $\pi_{o2}$: Likelihood precision for context cues; fixed (set to 0.001 in fitting since no external cues in experiment) - $\pi_{s1}$: Precision of Integrated dispositional prior [S]; free parameter - $\psi_{Ext}$: Weighting on non-neutral external states in situational prior [S]; free parameter - $\psi_{Split}$: Weighting on Bad and Good relative to Integrated in person prior [S]; free parameter (bounded 0--1) - $\psi_{Bad}$: Weighting on Bad relative to Good in person prior [S]; free parameter (bounded 0--1) - $\eta$: Learning rate for Dirichlet concentration parameters; fixed - $\omega$: Forgetting rate; fixed  Fitted values reported as group means: - Non-BPD: $\psi_{Bad}$ mean = 0.30; BPD: $\psi_{Bad}$ mean = 0.47
- **social_param:** $\psi_{Split}$ (degree of splitting -- propensity to use polarized "all-good"/"all-bad" representations of others' dispositions); $\psi_{Bad}$ (asymmetry of splitting -- relative balance of Bad vs. Good latent priors about others' moral character)
- **social_param_name:** $\psi_{Split}$
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC, likelihood ratio test (LRT, using mean log-likelihood ratio across participants)
- **how_model_fit:** individual-level-fit (maximum likelihood via bounded optimization, fmincon in MATLAB, single parameter set per participant fitted to both agents)
- **data_type_fit_to:** self-report ratings (moral character ratings, discretized into 11 bins)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 145 (102 non-BPD controls, 20 BPD, 23 BPD + DTC treatment); previously published data from Siegel et al. (2020)
- **population_category:** clinical
- **population_age_range:** 
- **ecological_validity:** Limited -- participants observe simulated agents making hypothetical moral choices (money vs. shocks to third party); no real social interaction; single dimension of moral character; explicit character ratings may not reflect implicit processes.
- **eligibility_flag:** 
- **concerns:** - Uses secondary data from Siegel et al. (2020); experimental design not optimized for the split-HMM - Small BPD sample (N = 20) limits power for group comparisons - BPD vs. DTC comparison is cross-sectional, not longitudinal - Parameter recovery poor for $\psi_{Ext}$ and $\pi_{o1}$ (acknowledged by authors -- design not optimized for these) - No external state manipulation in the task, so external attribution parameters are estimated from implicit attributions only ($\pi_{o2}$ fixed to 0.001) - Code available on request only, data available from original authors on request
- **limitations_reported:** The model leaves open several avenues for further enquiry; the experimental design was not optimized to test all aspects of the split-HMM; small number of trials (34) per participant; between-subjects design for DTC comparison; splitting modeled along single valence axis rather than multidimensional; future work needed to examine explicit vs. implicit social inference; parameter recovery for external attribution and first-level precision parameters was poor since experimental design not optimized for these; data not publicly available.
- **limitations_categorized:** task simplicity (unidimensional valence axis); limited ecological validity; sample size (small BPD group); secondary data analysis (design not optimized for model); poor parameter recovery for some parameters; limited generalizability (explicit judgments only); no open data
- **preregistered:** No
- **wc_rule1:** Partial
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 8.0
- **wc_total:** 8.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** yes
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - `ecological_validity`: MEDIUM confidence -- inferred from task design, not explicitly discussed under that label - `how_model_fit`: HIGH confidence -- explicitly described (MLE, fmincon) - `model_params` fitted values: MEDIUM -- only group means for $\psi_{Bad}$ reported; individual distributions shown in supplemental Figure S10 but not tabulated
- **cannot_find:** - Exact fitted mean values for all 5 free parameters across groups (only $\psi_{Bad}$ group means reported) - Individual-level parameter distributions for $\pi_{o1}$, $\pi_{s1}$, $\psi_{Ext}$ (shown in supplemental figures but values not tabulated)
- **other_notes:** - This paper is primarily a theoretical/computational modeling paper that introduces the split-HMM framework, with extensive simulations, and then validates on existing data. The empirical fitting section is secondary to the theoretical contribution. - The paper analyzes previously published data from Siegel et al. (2020) -- potential overlap should be checked if that paper is also in the review corpus. - A preprint version was previously available at https://psyarxiv.com/yvu2b/ - Published Online First August 21, 2023; journal issue 2024.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_bpd
- pop_healthy_adults
- rr_pop_bpd
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_depth = parametric
- spec_locus = target
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_bayesian
- tax_param_decay
- tax_param_precision
- tax_param_social_weight
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_primary_topic = trait_impression
- tax_rr_topic_trait_impression
- tax_topic_trait_impression
