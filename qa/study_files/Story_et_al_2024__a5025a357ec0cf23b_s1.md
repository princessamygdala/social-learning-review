# Story et al. (2024)

- **study_id:** `a5025a357ec0cf23b_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Story, G. W., Ereira, S., Valle, S., Chamberlain, S. R., Grant, J. E., & Dolan, R. J. (2024). A computational signature of self-other mergence in Borderline Personality Disorder. *Translational Psychiatry*, *14*, 473. https://doi.org/10.1038/s41398-024-03170-w
- **citation_short:** Story et al. (2024)
- **doi:** 10.1038/s41398-024-03170-w
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** Department of Psychiatry and Behavioral Neuroscience, University of Chicago, Chicago, IL, USA; etheextenttowhichlearningsignals betweenagent-specificupdating,whereinbeliefsofSelfandOther; mitations in mentalising are thought to underpin a assumed to be a shared reality [12, 20]; UCLCentreforComputationalPsychiatryandAgeingResearch,UniversityCollegeLondon,London,; DepartmentofPsychiatry,FacultyofMedicine,UniversityofSouthampton,Southampton,UK; DivisionofPsychiatry,UniversityCollegeLondon,London,UK; etheir ownlearningsignals toothers; University, London, UK; emails: g.story@ucl.ac.uk
- **code_url:** 

## Computational level
- **study_focus:** Mentalizing learning / self-other distinction in belief updating; how individuals with BPD fail to selectively assign learning signals to self vs. other agents during belief tracking.
- **study_focus_short:** Mentalizing learning / self-other distinction in belief updating
- **learning_mode_description:** - Learning mode: Learning from one's own and another's observations about a changing probability to update beliefs attributed to self and other   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (binary samples from Bernoulli distribution)     - Source type (social): other (store manager — fictive observer)       - Source content (social): outcome (samples observed by the other, including decoy/misleading information)   - Learning about:     - Target type (non-social): self (own belief about the underlying probability)       - Target content (non-social): state (world state; current probability estimate)     - Target type (social): other (store manager)       - Target content (social): state (mental state; other's belief about the underlying probability)
- **task_description:** Participants observed binary outcomes (umbrella vs. sunshade purchases) sampled from a changing Bernoulli distribution and periodically estimated the underlying probability from their own perspective or from the perspective of a fictive other person (store manager) who received partial or misleading information. The task included Shared, Privileged, and Decoy trial types that created divergent information streams for self and other.
- **task_paradigm:** Probabilistic ToM task
- **players:** Single agent (participant), single target (fictive other — store manager with partial/misleading information)
- **n_players:** single agent (1)
- **partner_type:** unclear
- **stimuli:** Binary purchase outcomes (pink umbrellas vs. yellow sunshades), cartoon face icons indicating trial type (open door = shared, closed door = privileged, computer disc = decoy), continuous probability rating scale
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - BPD participants showed significantly higher idiocentric updating (λ_Self) than controls (t(110) = 3.19, p = 0.002; Cohen's d = 0.64)   - No significant group difference in allocentric updating (λ_Other; t(110) = −1.50, p = 0.137)   - Idiocentric outcome-belief correlation (O_Self; B_Other) significantly greater in BPD group (t(110) = 3.12, p = 0.002)   - λ_Self positively related to BPD symptoms (BSL-95) across all participants (β = 0.0009, t(109) = 2.20, p = 0.030)   - λ_Self–BSL-95 relationship remained significant after controlling for demographics, depression, mania, impulsivity (β = 0.0014, t(82) = 2.73, p = 0.0078)   - Significant group × symptom interaction on λ_Self (β = −0.0007, t(109) = −2.58, p = 0.011)   - Sensitivity analysis excluding random responders: BPD vs. control λ_Self difference remained (t(93) = 2.78, p = 0.007; Cohen's d = 0.55)
- **effect_size:** Cohen's d = 0.64 (BPD vs. control on λ_Self); Cohen's d = 0.55 (sensitivity analysis); β_BSL-95 = 0.0014 (multiple regression); Bayes factor = 29.5 (winning model vs. symmetric λ model)
- **learning_from:** Self and other; own observations (privileged + shared samples) and other's observations (decoy + shared samples) of binary outcomes from a changing probability
- **learning_about:** Other's belief state (mental state — what the other person believes about the underlying probability) and own belief state about the world  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Reinforcement learning with unrestricted leakage and equal learning rates: B_Self(t) = B_Self(t-1) + α(PE_Self + λ_Other · PE_Other) + δ(0.5 − B(t-1)); B_Other(t) = B_Other(t-1) + α(PE_Other + λ_Self · PE_Self) + δ(0.5 − B(t-1)). Four free parameters: α (learning rate, shared), λ_Self (idiocentric leakage), λ_Other (allocentric leakage), τ (choice noise/temperature), δ (memory decay).
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning / Belief updating
- **all_models_tested:** 1. {"name": "λ Unrestricted, α equal", "family": "RW with leakage", "n_params": 5, "metric": "Bayesian model evidence (fixed-effects sum of log evidence + protected exceedance probability)"} 2. {"name": "λ Unrestricted, α unrestricted", "family": "RW with leakage", "n_params": 6, "metric": "Bayesian model evidence"} 3. {"name": "λ_Self = λ_Other, α equal", "family": "RW with symmetric leakage", "n_params": 4, "metric": "Bayesian model evidence"} 4. {"name": "λ_Self = λ_Other, α unrestricted", "family": "RW with symmetric leakage", "n_params": 5, "metric": "Bayesian model evidence"} 5. {"name": "λ = 0, α equal", "family": "RW agent-specific", "n_params": 3, "metric": "Bayesian model evidence"} 6. {"name": "λ = 0, α unrestricted", "family": "RW agent-specific", "n_params": 4, "metric": "Bayesian model evidence"}
- **model_mb_mf:** MF
- **model_params:** - α (learning rate, shared for Self and Other): governs sensitivity to new information; 0 < α < 1. Mean BPD: not separately reported. [Recovery r from parameter recovery analysis available in supplement] - λ_Self [S] (idiocentric leakage): degree to which self PE generalises to other's belief; bounded −1 to 1. Mean BPD = 0.14, mean control = −0.01 - λ_Other [S] (allocentric leakage): degree to which other's PE generalises to self's belief; bounded −1 to 1. No group mean explicitly reported for λ_Other - τ (choice temperature): stochasticity of responses; bounded 0.001 to 0.08 - δ (memory decay): drift of beliefs towards 0.5; bounded 0 to 1
- **social_param:** λ_Self (idiocentric leakage) — degree to which one's own prediction errors generalise to updating the representation of the other's belief. λ_Other (allocentric leakage) — degree to which the other's prediction errors generalise to updating one's own belief.
- **social_param_name:** λ_Self
- **social_param_value:** 0.14
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Bayesian model evidence (marginal likelihood approximated via sampling from prior, K=2000 samples); fixed-effects comparison (sum of log model evidence across participants); random-effects comparison (protected exceedance probability via Stephan et al. 2009; Rigoux et al. 2014)
- **how_model_fit:** individual-level-fit (MAP estimation per participant using fminunc in Matlab with Gaussian priors)
- **data_type_fit_to:** choice behavior (continuous probability estimates on probe trials; likelihood function = Beta distribution)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A — no neuroimaging
- **key_regions:** N/A — no neuroimaging
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 112 (38 BPD, 74 general population controls); BPD mean age 31.3 (SD 13.1), control mean age 32.4 (SD 13.0); 58% female in BPD, 57% in controls; 8% non-binary in both groups
- **population_category:** mixed
- **population_age_range:** M=31.3 (SD=13.1)
- **ecological_validity:** Low ecological validity — the task is "social only in its framing" (authors' own words); the other person is a fictive store manager with no actual social interaction. No interpersonal statistics (trustworthiness, generosity) are involved. The task measures domain-general meta-representational capacity rather than ecologically valid social interaction.
- **eligibility_flag:** 
- **concerns:** - The task is minimally social — "social only in its framing" with a fictive other; no real social interaction - BPD sample drawn from a clinical trial (brexpiprazole trial), which may introduce selection bias - Data collection interrupted by Covid-19; 9/38 BPD participants completed online vs. 29 in person; all controls completed online - High rate of random responding (15% of participants could not reject null hypothesis of chance) - Depression/mania assessed with different scales in BPD vs. control groups (clinician-rated vs. self-report), making comparison imperfect - Controls not screened for BPD diagnoses - λ_Self and λ_Other negatively correlated across participants (r = −0.19), though separately recoverable in parameter recovery - Parameter recovery for λ_Self and λ_Other only modest (r = 0.63 and 0.53 respectively), improving at lower choice noise
- **limitations_reported:** we could reject a null hypothesis of random responding in only 85% of participants"; "since data collection was interrupted by the Covid-19 pandemic, a small number of BPD participants (9 out of 38), and all control participants, completed the study online"; making the task easier (e.g., increasing stimulus presentation time) would reduce rates of unusable data; the p-FBT is "social only in its framing, and requires no inference about strictly interpersonal statistics"; the behavioural effect "is unlikely to depend on a participant's inference regarding the other's social characteristics"; question of specificity to BPD vs. transdiagnostic marker
- **limitations_categorized:** high rate of unusable data; mixed data collection modality (online vs. in-person); limited ecological validity; task simplicity (minimal social demands); limited generalizability (specificity to BPD uncertain); modest parameter recovery  ---  ## WILSON-COLLINS CHECKLIST  1. **Design a good experiment**: Yes — task specifically designed to dissociate self and other belief updating with privileged/shared/decoy trial types 2. **Design good models**: Yes — 6 models compared (nested: unrestricted vs. symmetric vs. no leakage; equal vs. unrestricted learning rates) 3. **Simulate, simulate, simulate**: Yes — model simulations shown in Fig. 1b,c demonstrating leakage effects on belief correlation; simulations used to establish parameter recovery 4. **Fit the parameters**: Yes — MAP estimation with Gaussian priors, individual-level fitting 5. **Check parameter recovery**: Yes — 560 simulated participants; Pearson correlations between generative and recovered parameters reported (λ_Self r = 0.63, λ_Other r = 0.53; improves to r = 0.85 and 0.82 at low noise) 6. **Check model recovery**: No — no confusion matrix or model recovery analysis reported 7. **Fit real data and compare models**: Yes — fixed-effects Bayes factor and protected exceedance probability reported 8. **Validate the winning model**: Partial — model fits shown visually for sample participants (Fig. 3c); model-free analyses (outcome-belief correlations) converge with model-based findings, but no formal posterior predictive check reported 9. **Analyze the winning model**: Yes — group comparison of parameters, correlation with symptom scores, sensitivity analyses 10. **Report results transparently**: Partial — control participant data and code shared on GitHub; patient data available on request due to confidentiality  ---  ## PREREGISTERED  Not reported (the clinical trial was registered at ClinicalTrials.gov NCT03418675, but the p-FBT analysis itself was not described as preregistered)  ---  ## FLAGGED FIELDS
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 8.0
- **wc_total:** 8.0

## Context flags
- **ctx_copresence:** unclear
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `model_params` (MEDIUM): exact mean fitted values for α, τ, δ not reported by group in main text; only λ_Self means reported by group   - `ecological_validity` (HIGH): authors themselves note the task is "social only in its framing"   - `wc_8` (MEDIUM): no formal posterior predictive check; convergence of model-free and model-based analyses serves as informal validation
- **cannot_find:** - Mean fitted values for α, δ, τ by group (not reported in main text or supplement tables accessible)   - Formal model recovery (confusion matrix) — not performed   - λ_Other group means (BPD mean not explicitly stated, only that no significant difference)
- **other_notes:** - This paper builds on prior work by Ereira et al. (2018, 2020) who developed the p-FBT   - The task is explicitly described as "social only in its framing" — this should be flagged for the social degree rating   - The leakage model is a novel computational operationalization of "psychic equivalence" from mentalizing-based theories of BPD   - Social degree: 1/3 — the social element is purely in framing (a fictive store manager); no actual social interaction, no interpersonal inference, no real social agent
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
- spec_target = partly
- tax_domain_B_inference_modelling_others
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_bayesian
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_primary_topic = self_other_boundary
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_mentalizing
- tax_rr_topic_self_other_boundary
- tax_topic_mentalizing
- tax_topic_self_other_boundary
