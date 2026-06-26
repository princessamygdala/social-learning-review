# Ereira et al. (2020)

- **study_id:** `a4b676be68b05d63f_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Ereira, S., Hauser, T. U., Moran, R., Story, G. W., Dolan, R. J., & Kurth-Nelson, Z. (2020). Social training reconfigures prediction errors to shape Self-Other boundaries. *Nature Communications*, *11*, 3030. https://doi.org/10.1038/s41467-020-16856-8
- **citation_short:** Ereira et al. (2020)
- **doi:** 10.1038/s41467-020-16856-8
- **publication_type:** peer-reviewed journal
- **year:** 2020.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** UCLCentreforComputationalPsychiatryandAgeingResearch,UCL,LondonWC1B5EH,UK; ether a Self-Other distinction is suscep- behaviour in order to; etheragent-specificityadaptsto; ethods) to subjects’ choice; CentreforHumanNeuroimaging,; UCL,LondonWC1N3BG,UK; ether any beha-; etheobserved; emails: samuel.ereira.14@ucl.ac.uk
- **code_url:** 

## Computational level
- **study_focus:** Self-Other boundary learning; learning how to distinguish or merge self-attributed and other-attributed prediction error signals as a function of shared social experience
- **study_focus_short:** Self-Other boundary learning
- **learning_mode_description:** - Learning mode: Learning from shared vs. unshared sensory outcomes how to attribute prediction errors to self vs. other agents   - Learning from:     - Source type (non-social): world       - Source content (non-social): outcome (Bernoulli samples — sensory prediction errors)     - Source type (social): other (co-player avatar)       - Source content (social): outcome (other's PE from observed/unobserved samples)       - If joint on shared trials: mark as **joint**   - Learning about:     - Target type (social): self and other (self-other boundary / agent-specificity)       - Target content (social): state (mental state; beliefs about Bernoulli parameter attributed to self vs. other)
- **task_description:** Participants tracked a drifting Bernoulli parameter while simultaneously estimating a co-player's false belief about the same parameter. Trials were "privileged" (self-only information), "shared" (both see), or "decoy" (misleading information to other). Two social contexts differed in the proportion of shared trials (Hi-Share: 50%; Lo-Share: 12.5%) during training, with identical proportions at test 24 hours later during fMRI.
- **task_paradigm:** Probabilistic ToM task
- **players:** Single agent (participant), multi-target (2 co-player avatars representing real previous participants; one Hi-Share, one Lo-Share)
- **n_players:** multi-target (3+)
- **partner_type:** human (live)
- **stimuli:** Bernoulli outcomes (pink/yellow), cartoon avatars, trial-type indicators (privileged/shared/decoy), continuous probability scale for probe responses
- **method:** fMRI / behavioural
- **method_full:** fMRI, behavioural, quantitative MRI (magnetisation transfer)
- **main_result:** - In the testing session (identical task statistics), performance was significantly worse in the Hi-Share context (F(1,39) = 6.76, repeated measures ANOVA) - Interaction between context and probe trial on performance (F(1,39), p = 0.023); Hi-Share impaired Self probes (t(39) = 2.96, p = 0.005) but not Other probes - Self-Other belief correlation higher in Hi-Share than Lo-Share in both training (F(1,39) = 21.7) and testing (F(1,39) = 3.8) - Hi-Share behaviour best explained by models with leak parameter (λ); Lo-Share by models without λ - Transfer to perspective-taking task: corrected drift rate change differed by avatar (F(1,45) = 7.4, p = 0.009) - Self-Other PE classification accuracy higher in Lo-Share than Hi-Share (t(39) = 2.1, p = 0.041) - Cross-decoding (PE_self predicting PE_other) higher in Hi-Share than Lo-Share (t(39) = 2.75, p = 0.009) - Cross-decoding difference correlated with λ:α ratio (r = 0.41, p = 0.009) - vmPFC white matter MT correlated with cross-decoding difference (844 voxels, p < 0.001 FWE) - vmPFC BOLD tracked P(share) at η = 0.01 (192 voxels, p = 0.008, SVC) - Left temporal pole tracked P(share) at η = 0.025 (583 voxels, p = 0.006 FWE) - λ predicted temporal discounting propensity (p = 0.005, permutation test); adding fMRI cross-decoding improved prediction (p = 0.016)
- **effect_size:** - PE classification: Lo vs Hi-Share, d not reported; t(39) = 2.1 - Cross-decoding: Hi vs Lo-Share, t(39) = 2.75 - Cross-decoding ~ λ:α correlation: r = 0.41 - vmPFC MT ~ cross-decoding: 844 voxels cluster - vmPFC contrast ~ cross-decoding: r = 0.35 - λ:α ~ discount factor: ρ = −0.32 - MT ~ discount factor: p = 0.022 SVC - vmPFC ~ temporal cortex contrast estimates: r = 0.45
- **learning_from:** Self and other's sensory prediction errors from Bernoulli outcomes; source: self + other (co-player)
- **learning_about:** Self-Other boundary / agent-specificity of belief representations; target: self and other (beliefs about environment attributed to each agent)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Rescorla-Wagner with leak: B_{t+1} = B_t + α·PE_self + δ(0.5 − B_t) + λ·PE_other; separate models won for different contexts. Hi-Share: model with λ + 4 learning rates (α_s1, α_s2, α_o1, α_o2) + 2 τ + 1 δ + 1 λ (M68, 8 params). Lo-Share training: M4 (α + τ + δ, 3 params, no λ). Lo-Share testing: M13 (α_s, α_o + τ_s, τ_o + δ, 4 params, no λ). Hi-Share training: M65 (4α + 2τ + 1λ, 7 params).
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "72 RW variants (M1-M72)", "family": "Rescorla-Wagner", "n_params": "2-10", "metric": "BIC (summed across subjects)"}]. Specifically, 72 models crossing: learning rate (1 shared / 2 self-other / 2 shared-vs-privileged / 4 fully separated), temperature (1 or 2), memory decay (0, 1, or 2), leak (0, 1, or 2). Winning models: Lo-Share training M4 (3 params), Hi-Share training M65 (7 params), Lo-Share testing M13 (4 params), Hi-Share testing M68 (8 params).
- **model_mb_mf:** MF
- **model_params:** - α (learning rate) — governs weight on PE for belief update. In winning model M68: 4 separate learning rates: α_s1 [S] (self, privileged/decoy trials), α_s2 [S] (self, shared trials), α_o1 [S] (other, privileged/decoy trials), α_o2 [S] (other, shared trials). α_other > α_self (t(39) = −2.27, p = 0.029). - τ (decision temperature) — governs choice stochasticity. In M68: 2 separate (τ_s, τ_o) [S]. - δ (memory decay) — rate at which beliefs drift toward 0.5. In M68: 1 shared parameter. - λ (Self-Other leak) [S] — governs how much the irrelevant agent's PE updates the relevant agent's belief. In M68: 1 shared parameter. Key social parameter.  (Mean fitted values not reported in main text or supplement figures in numeric form.)
- **social_param:** λ (Self-Other leak parameter) — captures the degree to which one agent's prediction error leaks into belief updates for the other agent. Higher λ indicates more Self-Other mergence.
- **social_param_name:** α
- **social_param_value:** 4
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (summed across subjects)
- **how_model_fit:** individual-level-fit (maximum likelihood estimation via fmincon in MATLAB; separate fit per subject per dataset)
- **data_type_fit_to:** choice behavior (probe trial reports on continuous probability scale)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) + MVPA (searchlight multi-voxel pattern analysis) + cross-decoding (linear regression on PE patterns)
- **contrast:** - |PE_self| parametric modulator (GLM, unsigned PE) - |PE_other| parametric modulator (GLM, unsigned PE) - Self vs Other PE classification (LASSO logistic regression on multi-voxel patterns) - Cross-decoding: train on PE_self patterns, test on PE_other (and vice versa), Hi-Share vs Lo-Share - P(share) regressor in vmPFC ROI and whole-brain - White matter MT ~ cross-decoding difference (whole-brain regression)
- **key_regions:** Self- and Other-attributed PEs in extrastriate visual cortex, parietal cortex, and supplementary motor cortex. Self-Other PE overlap modulated by training in these regions. vmPFC white matter MT associated with degree of PE reconfiguration (peak: 12.8, 59.2, −18.4). vmPFC BOLD tracks probability of sharing (peak: 3, 46, −15). Left temporal pole tracks P(share) at higher frequency (peak: −62, −16, −16).
- **key_regions_abbrev:** vmPFC, mPFC, TP, AI, parietal, SMA
- **coordinates_peak:** GLM |PE_self|: - Extrastriate/parietal: 29, −54, 44 (cluster 1835 voxels) - Right lateral occipital: 47, −60, −6 (cluster 981 voxels) - Left lateral occipital: −44, −66, −5 (cluster 802 voxels)  GLM |PE_other|: - Early visual cortex: −9, −93, 2 (cluster 2365 voxels) - Right parietal: 36, −77, 32 (cluster 1486 voxels) - Right intraparietal: 35, −39, 41 (cluster 723 voxels) - Left occipital: −29, −84, 26 (cluster 541 voxels)  Searchlight |PE_self|: - Right parietal/occipital: 41, −65, 24 (cluster 1632 voxels) - Right parietal: 29, −53, 48 (cluster 1230 voxels) - Right supplementary motor: 18, −21, 54 (cluster 1223 voxels)  Searchlight |PE_other|: - Left occipital: −18, −92, 11 (cluster 1586 voxels)  White matter MT ~ cross-decoding: - Right vmPFC white matter: 12.8, 59.2, −18.4 (844 voxels, p < 0.001 FWE)  P(share) tracking (η = 0.01): - Bilateral vmPFC: 3, 46, −15 (192 voxels, p = 0.008 SVC)  P(share) tracking (η = 0.025): - Left lateral temporal / temporal pole: −62, −16, −16 (583 voxels, p = 0.006 FWE)  vmPFC white matter MT ~ discount factor: - vmPFC WM sub-cluster: 201 voxels, p = 0.022 SVC
- **analysis_type:** both (whole-brain for PE localisation, MT analysis, and P(share) temporal cortex; ROI/SVC for vmPFC P(share) and vmPFC MT ~ discount factor)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** N = 47 recruited (26 female), ages 19–54; N = 46 (25 female, mean age 26.5, SD 7.8) for perspective-taking analysis; N = 40 (22 female, mean age 26.8, SD 8.1) for fMRI and all other analyses (6 did not complete day 3; 1 excluded for not understanding tasks)
- **population_category:** healthy adults
- **population_age_range:** 19–54
- **ecological_validity:** Moderate. Task uses a cover story (shop assistant tracking sales with a manager) to provide social context, but learning is about abstract Bernoulli parameters, not naturalistic social cues. The other "agent" is represented by a cartoon avatar linked to a real previous participant's data, but there is no live social interaction. Transfer to a visual perspective-taking task suggests some ecological generalizability. Authors acknowledge the task may not engage processes that are "social per se.
- **eligibility_flag:** 
- **concerns:** The winning model differs across the four datasets (Hi/Lo-Share x Train/Test), making it difficult to directly compare parameters across conditions. The fMRI analysis used median parameters across subjects from the most complex winning model (M68) for all subjects in both conditions, which may not optimally capture Lo-Share dynamics. The MT analysis is cross-sectional (correlational, not longitudinal), so causal claims about myeloarchitecture driving PE reconfiguration are limited. The vmPFC P(share) analysis tested 5 arbitrary values of η with Bonferroni correction rather than fitting η. The correlation between vmPFC contrast and cross-decoding (r = 0.35) was only significant after excluding 2 outliers (|Z| > 2.5).
- **limitations_reported:** Authors acknowledge: the FBT may not engage cognitive processes that are social per se — it merely requires tracking two random variables; the behavioural transfer may reflect non-social learning; the notion that future Self is represented like Other is speculative; a hidden variable such as general task engagement or cognitive control might explain the association between Self-Other distinction and temporal discounting; they did not measure longitudinal structural brain changes but correlated neural microstructure with PE reconfiguration cross-sectionally; they did not manipulate temporal contingency between signals per se, using proportion of shared trials as a proxy.
- **limitations_categorized:** limited ecological validity; task may not be social per se; correlational brain-behaviour analysis; no longitudinal structural imaging; confound of general cognitive ability; speculative interpretation of temporal discounting link; proxy measure for temporal contingency
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
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params mean fitted values: MEDIUM confidence — parameter estimates shown in Supplementary Fig 1 as bar plots but exact numeric values not reported in text - ecological_validity: MEDIUM — interpretation of "socialness" is debated by the authors themselves
- **cannot_find:** - Exact mean fitted parameter values (shown graphically in Supp Fig 1 but not tabulated numerically)
- **other_notes:** This is a single study (not multi-study). The paper also includes a drift-diffusion model fit to the perspective-taking task and a hyperbolic discounting model fit to the intertemporal choice task, but these are secondary/transfer analyses, not the core computational model of social learning. The paper is notable for demonstrating that Self-Other boundaries in PE representations are plastic and shaped by statistical structure of social experience. Data and code are openly available on OSF.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_depth = parametric
- spec_locus = target
- spec_neural = shared
- spec_source = social
- spec_target = partly
- tax_domain_B_inference_modelling_others
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_decay
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = self_other_boundary
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_mentalizing
- tax_rr_topic_self_other_boundary
- tax_topic_mentalizing
- tax_topic_self_other_boundary
