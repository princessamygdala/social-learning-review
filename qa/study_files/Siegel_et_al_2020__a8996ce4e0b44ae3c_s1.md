# Siegel et al. (2020)

- **study_id:** `a8996ce4e0b44ae3c_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Siegel, J. Z., Curwell-Parry, O., Pearce, S., Saunders, K. E. A., & Crockett, M. J. (2020). A computational phenotype of disrupted moral inference in borderline personality disorder. *Biological Psychiatry: Cognitive Neuroscience and Neuroimaging*, *5*(12), 1134–1141. https://doi.org/10.1016/j.bpsc.2020.07.013
- **citation_short:** Siegel et al. (2020)
- **doi:** 10.1016/j.bpsc.2020.07.013
- **publication_type:** peer-reviewed journal
- **year:** 2020.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** ETHODS:ParticipantswithBPD(n=43;20untreatedand23DTC-treated)andcontrol participantswithoutBPD; ethepotentialforcombiningobjectivebehavioralparadigmswith; ethods) and were excluded from the analysis; ether they are helpful and trustworthy or; lab and online settings (17); mpirical work suggests that; mited in their; ethods
- **code_url:** 

## Computational level
- **study_focus:** Moral inference / moral character learning — how individuals with BPD form and update beliefs about others' moral character, and sensitivity to DTC treatment.
- **study_focus_short:** Moral inference / moral character learning
- **learning_mode_description:** - Learning mode: Learning from observing another agent's moral choices about that agent's moral character     - Learning from:       - Source type (social): other (observed agent/"Decider")       - Source content (social): action/policy (choices to inflict shocks for money)     - Learning about:       - Target type (social): other (observed agent/"Decider")       - Target content (social): state (mental state; moral character/preferences)
- **task_description:** Participants predicted and observed the choices of two agents ("Deciders") who repeatedly decided whether to inflict painful electric shocks on a victim in exchange for varying amounts of money; periodically, participants rated their subjective impressions of each agent's moral character and their certainty about those impressions.
- **task_paradigm:** Punishment / third-party
- **players:** Single agent (participant), multi-target (2 agents: "good" and "bad" Decider)
- **n_players:** dyadic (2)
- **partner_type:** unclear
- **stimuli:** Monetary amounts paired with shock quantities (numerical), binary choice outcomes, character and certainty rating scales (0–100 nasty-to-nice; 0–1 uncertain-to-certain)
- **method:** online / behavioural
- **method_full:** behavioural (online for controls; in-lab for BPD groups)
- **main_result:** - Main Results:     - BPD vs. non-BPD: Agent x Group interaction on uncertainty ratings (β = −0.263 ± 0.080, t = −3.284, p = .001)     - BPD vs. non-BPD: Agent x Group interaction on learning rates (β = −0.167 ± 0.044, t = −3.827, p < .001)     - BPD held less uncertain impressions of bad agent (β = −0.162 ± 0.058, t = −2.805, p = .005)     - BPD slower to update beliefs about bad agent (β = −0.109 ± 0.034, t = −3.222, p = .001)     - BPD faster to update beliefs about good agent (β = 0.062 ± 0.027, t = 2.287, p = .022)     - DTC vs. untreated BPD: Agent x Group interaction on uncertainty ratings (β = 0.277 ± 0.095, t = 2.904, p = .003)     - DTC vs. untreated BPD: Agent x Group interaction on learning rates (β = 0.589 ± 0.052, t = 11.588, p < .001)     - DTC more uncertain impressions of bad agent (β = 0.188 ± 0.067, t = 2.802, p = .005)     - DTC faster learning rates for bad agent (β = 0.543 ± 0.040, t = 13.698, p < .001)   - Note: No Cohen's d, r², η², or other standardized effect sizes reported beyond standardized betas from robust regression.
- **effect_size:** - Main Results:     - BPD vs. non-BPD: Agent x Group interaction on uncertainty ratings (β = −0.263 ± 0.080, t = −3.284, p = .001)     - BPD vs. non-BPD: Agent x Group interaction on learning rates (β = −0.167 ± 0.044, t = −3.827, p < .001)     - BPD held less uncertain impressions of bad agent (β = −0.162 ± 0.058, t = −2.805, p = .005)     - BPD slower to update beliefs about bad agent (β = −0.109 ± 0.034, t = −3.222, p = .001)     - BPD faster to update beliefs about good agent (β = 0.062 ± 0.027, t = 2.287, p = .022)     - DTC vs. untreated BPD: Agent x Group interaction on uncertainty ratings (β = 0.277 ± 0.095, t = 2.904, p = .003)     - DTC vs. untreated BPD: Agent x Group interaction on learning rates (β = 0.589 ± 0.052, t = 11.588, p < .001)     - DTC more uncertain impressions of bad agent (β = 0.188 ± 0.067, t = 2.802, p = .005)     - DTC faster learning rates for bad agent (β = 0.543 ± 0.040, t = 13.698, p < .001)   - Note: No Cohen's d, r², η², or other standardized effect sizes reported beyond standardized betas from robust regression.
- **learning_from:** Other (observed agent's choices — whether to shock for money); social
- **learning_about:** Other (observed agent's moral character / moral preferences); social  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Hierarchical Bayesian learning model with dynamic learning rate (from Siegel et al., 2018; Mathys et al., 2011, 2014 — essentially a variant of the Hierarchical Gaussian Filter, HGF)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** 1. {"name": "Dynamic learning rate model (HGF-based)", "family": "Bayesian belief updating", "n_params": "not reported in main text", "metric": "random-effects Bayesian model selection"}   2. {"name": "Fixed learning rate model", "family": "Rescorla-Wagner-like", "n_params": "not reported in main text", "metric": "random-effects Bayesian model selection"}   3. {"name": "Separate fixed learning rates (positive/negative)", "family": "Rescorla-Wagner-like (dual LR)", "n_params": "not reported in main text", "metric": "random-effects Bayesian model selection"}
- **model_mb_mf:** Bayesian
- **model_params:** The paper states that participant-specific parameters were identified describing how beliefs about agents' morality were updated, including dynamic learning rates (which vary trial-by-trial as a function of belief precision). Exact parameter names and fitted values are not reported in the main text. The model is described as per Siegel et al. (2018) and Mathys et al. (2011, 2014). Key derived variable: dynamic learning rate (higher when beliefs are less precise). Mean fitted parameter values not reported.   - Confidence: LOW — parameter details likely in supplement (not accessible)
- **social_param:** Dynamic learning rate — captures how rapidly beliefs about others' moral character are updated; differs by agent type (good vs. bad) and clinical group. [S]
- **social_param_name:** Dynamic learning rate
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Random-effects Bayesian model selection (BMS)
- **how_model_fit:** individual-level-fit (hierarchical Bayesian estimation, participant-specific parameters)
- **data_type_fit_to:** choice behavior (trial-by-trial predictions of agent choices)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 149 total (106 non-BPD controls [online]; 20 untreated BPD; 23 DTC-treated BPD). Ages matched (~39–42 years).
- **population_category:** clinical
- **population_age_range:** 39–42
- **ecological_validity:** The task involves observing hypothetical agents making moral decisions (shock vs. money trade-offs), which is somewhat abstract but captures a meaningful social inference process. Online delivery for controls; in-lab for BPD groups introduces potential setting differences. The agents are not real interaction partners — participants observe pre-programmed choice sequences.
- **eligibility_flag:** 
- **concerns:** - Supplement not accessible — model parameters, exact formulae, number of free parameters, parameter recovery, and model recovery details cannot be verified from the main text alone.   - Control group tested online; BPD groups tested in-lab — potential setting confound (though authors cite prior work showing comparable results).   - No neuroimaging — implementation level is N/A.   - Cross-sectional design for DTC comparison (not randomized to DTC vs. untreated).   - Multiple participants on psychotropic medication.
- **limitations_reported:** A major limitation of this study is that we chose to investigate moral inference in individuals with a primary diagnosis of BPD, rather than considering symptom clusters associated with a primary diagnosis of BPD"; "disruptions to moral inference are not specific to BPD as a category, but rather relate to aspects of cognition that are predictive of a variety of disorders"; "data collection in the present study relied on the availability of a small population of participants with BPD who had completed DTC treatment"; "sample size was determined by participant availability"; "a number of DTC-treated and untreated patients were receiving psychotropic medication
- **limitations_categorized:** categorical diagnosis vs. dimensional; limited generalizability; sample size; convenience sampling; medication confound
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 6.0
- **wc_total:** 6.0

## Context flags
- **ctx_copresence:** unclear
- **ctx_observability:** yes
- **ctx_audience:** yes
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_params: LOW — exact parameters, number of free parameters, and fitted values not reported in main text; described by reference to prior papers (Siegel et al., 2018; Mathys et al., 2011, 2014). Likely in supplement.   - wc_3 (simulate): LOW — may be in supplement   - wc_5 (parameter recovery): LOW — may be in supplement   - wc_6 (model recovery): LOW — may be in supplement   - wc_10 (transparency): MEDIUM — no data/code sharing mentioned in main text   - effect_size: MEDIUM — only standardized betas from robust regression reported; no traditional effect sizes (d, r², η²)
- **cannot_find:** Exact model formula; number of free parameters per model; mean fitted parameter values; parameter recovery results; model recovery results; simulation results; data/code availability statement. All of these are likely in the supplement (referenced multiple times as "see Supplemental Methods" and "see Supplemental Results") which is not locally available.
- **other_notes:** The model is essentially the Hierarchical Gaussian Filter (HGF) from Mathys et al. (2011, 2014) applied to moral inference, as developed in Siegel et al. (2018). The key insight is that in healthy adults, beliefs about "bad" agents are maintained with greater uncertainty (enabling faster updating/forgiveness), whereas BPD patients show the opposite pattern. The DTC treatment group shows a pattern more similar to healthy controls specifically for bad-agent beliefs. Supplement not accessible locally — this limits extraction of algorithmic details. Setting `re_extract_flag: true` for supplement-dependent fields.
- **re_extract_flag:** true (supplement not accessible; multiple algorithmic fields depend on it)

## Taxonomy / categorization (active codes only)
- pop_bpd
- pop_healthy_adults
- rr_pop_bpd
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_mentalizing_inference
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_F_affective_moral
- tax_mod_action_observation
- tax_mod_mentalizing_inference
- tax_model_HGF
- tax_model_bayesian
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_precision
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_F_affective_moral
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_learning_rate
- tax_rr_param_precision
- tax_rr_primary_topic = moral_harm
- tax_rr_secondary_topic = trait_impression
- tax_rr_topic_moral_harm
- tax_rr_topic_trait_impression
- tax_topic_moral_harm
- tax_topic_trait_impression
