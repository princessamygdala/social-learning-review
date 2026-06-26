# Levorsen et al. (2021)

- **study_id:** `a18b63d00c750fecf_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Levorsen, M., Ito, A., Suzuki, S., & Izuma, K. (2021). Testing the reinforcement learning hypothesis of social conformity. *Human Brain Mapping*, *42*(5), 1328–1342. https://doi.org/10.1002/hbm.25296
- **citation_short:** Levorsen et al. (2021)
- **doi:** 10.1002/hbm.25296
- **publication_type:** peer-reviewed journal---
- **year:** 2021.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** UniversityofTechnology,Kochi,Japan sizedthatsocialconformityandreinforcementlearninghaveacommonneuralmech-; SchoolofEconomicsand processes have never been directly compared; therefore, the extent to which they; mity,whichrefersto Rijpkema,Smidts,&Fernandez,2009)foundthattheposteriormedial; mity and reinforcement learning tasks inside a functional magnetic resonance; CenterforFutureDesign,Kochi Ourpreferencesareinfluencedbytheopinionsofothers; UniversityofTechnology, sharedacommonneuralmechanismhadremainedunclear; mitythatincludestheposteriormedialfrontalcortex(pMFC),anterior; ethesebrainregion
- **code_url:** 

## Computational level
- **study_focus:** Social conformity — testing whether social conformity and nonsocial reinforcement learning share a common neural mechanism
- **study_focus_short:** Social conformity
- **learning_mode_description:** - Learning mode: Learning from reward outcomes about reward probability of choice options (reinforcement learning task); learning from group opinion discrepancy about preference adjustment (social conformity task)   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (reward win/loss in RL task)     - Source type (social): group       - Source content (social): state (group opinion/rating)   - Learning about:     - Target type (non-social): world (slot machine reward probabilities)       - Target content (non-social): outcome (expected reward value)     - Target type (social): self (own preference/attractiveness rating)       - Target content (social): state (own preference alignment with group)
- **task_description:** In the social conformity task, participants rated the attractiveness of female faces on a 10-point scale and then observed group ratings that were systematically manipulated to differ from their own; they later re-rated the faces without group feedback to measure conformity. In the reinforcement learning task, participants chose between two slot machines with drifting reward probabilities to maximize wins.
- **task_paradigm:** Conformity / Asch-style
- **players:** Single agent (participant), group context (fictitious group of university students providing ratings in conformity task); single agent (participant) in RL task
- **n_players:** single agent (1)
- **partner_type:** computer (algorithmic)
- **stimuli:** Female face photographs (100 Caucasian women), 10-point attractiveness scale, group ratings (social conformity task); colored slot machine images with binary win/loss outcomes (reinforcement learning task)
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Significant social conformity effect: second ratings influenced by group rating after controlling for regression-to-mean (t[24] = 2.18, p = .02, d = 0.43) - Significant regression-to-mean effect (t[24] = -15.81, p < .001, d = 3.16) - RL task: participants selected higher-probability option 59.9% of trials, significantly above chance (t[24] = 6.22, p < .001, d = 1.24) - BMS: RL model had 100% exceedance probability over fixed-probability model - No correlation between conformity effects and learning rate (r[23] = -.09, p = .66) - Univariate fMRI: Activation overlaps in pMFC, bilateral insula (social conflict + unsigned PE), and striatum (social conflict + signed PE) - Correlation-based MVPA: No significant positive correlations in any of the 7 overlapped regions (all ps > .41) - Classifier-based MVPA: dmPFC (accuracy = 59%, p = .004) and right putamen (accuracy = 56%, p = .016) showed significantly distinct patterns between social conflict and prediction error - Searchlight MVPA: 9 significant clusters showing distinct (not shared) patterns; no clusters showing shared patterns
- **effect_size:** d = 0.43 (conformity effect), d = 3.16 (regression-to-mean), d = 1.24 (RL above chance), exceedance probability = 100% (RL model vs. fixed model), MVPA classification accuracies: 59% dmPFC, 56% right putamen (both significantly above 50%)
- **learning_from:** Group opinion (social conformity task); reward outcome on chosen slot machine (RL task)
- **learning_about:** Own attractiveness preferences / alignment with group (social conformity task); reward probabilities of slot machines (RL task)---  ## ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Q-learning (1 α, 1 β; MAP estimation with Beta(2,2) prior on α, Gamma(2,3) prior on β)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Q-learning model", "family": "Q-learning", "n_params": 2, "metric": "Laplace approximated log model evidence / BMS"}, {"name": "Fixed-probability model", "family": "Descriptive", "n_params": 1, "metric": "Laplace approximated log model evidence / BMS"}]
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): constrained 0–1, Beta(2,2) prior; fitted values not reported [S: No — applies to RL task only] - β (inverse temperature): constrained positive, Gamma(2,3) prior; fitted values not reported  Note: The computational model was applied to the reinforcement learning task only, not to the social conformity task. The social conformity effect was assessed via multiple regression (gap and first rating predicting rating change), not via a computational model. No social parameters were estimated.
- **social_param:** None — the computational model was fit only to the nonsocial RL task. The social conformity task used regression analysis, not a computational model.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Laplace approximated log model evidence with Bayesian Model Selection (BMS; random effects)
- **how_model_fit:** individual-level-fit (MAP estimation per participant)
- **data_type_fit_to:** choice behavior (RL task only)---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) + MVPA (correlation-based and classifier-based)
- **contrast:** - Social conformity task: absolute gap (|participant rating − group rating|) as parametric modulator at feedback onset - RL task: signed PE and unsigned PE (from Q-learning model) as parametric modulators at feedback onset - MVPA: cross-task classification (social conflict vs. unsigned PE in pMFC/insula; social conflict vs. signed PE in striatum)
- **key_regions:** Social conflict positively correlated with pMFC (dmPFC, pre-SMA) and bilateral anterior insula; negatively with bilateral striatum. Unsigned PE positively correlated with pMFC and bilateral anterior insula. Signed PE positively correlated with bilateral putamen and left NAcc. MVPA showed distinct (not shared) patterns in dmPFC and right putamen.
- **key_regions_abbrev:** NAcc, putamen, striatum, mPFC, dmPFC, ACC, insula, AI
- **coordinates_peak:** Social conformity task (Table 1): - dmPFC: 8, 48, 38 - Right anterior insula: 38, 22, -4 - Left anterior insula: -34, 20, -16 - Pre-SMA: 12, 20, 68 - Left striatum (caudate body): -18, -8, 20 - Left caudate tail: -14, -20, 22 - Left putamen: -32, -16, 6 - Left caudate head: -18, 22, 14 - Left NAcc: -18, 10, -8 - Right striatum (caudate head): 14, 28, 0 - Right caudate body: 20, 16, 20 - Right putamen: 36, -8, -4 - Right caudate tail: 22, -24, 22 - Right NAcc: 16, 10, -12  RL task (Table 3): - mPFC: 16, 64, 2 - Pre-SMA/dmPFC: -2, 16, 54 - Left anterior insula: -44, 16, -10 - Right anterior insula: 38, 18, -4 - Left putamen: -34, -4, 2 - Right putamen: 32, -6, 14 - Left NAcc: -12, 14, -4  Overlap regions (Table 5): - dmPFC: 8, 28, 44 - Pre-SMA: 6, 16, 62 - Right anterior insula: 38, 22, -4 - Left anterior insula: -36, 20, -8 - Right posterior putamen: 32, -12, 2 - Left posterior putamen: -30, -12, 6 - Left NAcc: -18, 10, -8  Searchlight MVPA distinct clusters (Table 7): - dmPFC: 16, 24, 60 - dACC: -2, 30, 38 - Pre-SMA: 4, 16, 66 - Right anterior insula: 44, 20, -12 - Left anterior insula 1: -28, 24, 0 - Left anterior insula 2: -42, 16, -4 - Left posterior putamen: -24, 10, -4 - Right NAcc: 4, 12, -4 - Left anterior putamen: -32, 2, 4
- **analysis_type:** both (ROI-based within anatomical ROIs + whole-brain outside ROIs)---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 29 recruited (right-handed females); N = 25 final sample (4 excluded: 1 excessive head movement, 2 strong doubts about manipulation, 1 technical problems); mean age = 22.1 years
- **population_category:** undergraduates
- **population_age_range:** M=22.1
- **ecological_validity:** Low — social conformity task uses fictitious group ratings of face attractiveness (not real-time social interaction); RL task is a standard slot machine paradigm. No real social interaction occurs. Female-only sample limits generalizability.
- **eligibility_flag:** The computational model (Q-learning) is applied only to the nonsocial RL task, not to the social conformity task. The social conformity component uses regression analysis, not computational modeling. The paper's primary goal is to compare neural representations across tasks rather than to model social learning computationally. This is borderline for inclusion — the social conformity task involves learning-like preference change but is not modeled computationally. Flag: "Computational model applied to nonsocial RL task only; social conformity assessed via regression, not computational model. Borderline: social learning not computationally modeled.
- **concerns:** - Computational model fit only to the nonsocial RL task; social conformity analyzed with regression only - Small sample (N = 25, all female) - Lenient univariate threshold (p < .005 uncorrected within ROIs) to avoid false negatives - Mean fitted parameter values for Q-learning model not reported - No parameter recovery or model recovery analyses - The paper is primarily about comparing neural representations, not about computational modeling of social learning per se - Data available only upon request
- **limitations_reported:** Social conformity is not a unitary phenomenon and some forms may be more similar to RL than the paradigm tested here; the face attractiveness rating task captures motivation for social approval or self-concept maintenance but not accuracy motivation; the paradigm may not generalize to situations where group opinion can serve as a strong teaching signal; results may not generalize to other social conformity tasks where social conflict functions as a teaching signal
- **limitations_categorized:** Limited generalizability (single paradigm); task simplicity; limited ecological validity; sample size; female-only sample
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `model_params`: MEDIUM — mean fitted values of α and β not reported in paper - `social_param`: HIGH — confirmed no social parameter (model fit to RL task only) - `eligibility_flag`: HIGH — computational model not applied to social learning component - `ecological_validity`: MEDIUM — assessment based on task description
- **cannot_find:** - Mean fitted parameter values for α and β - Individual-level model fit statistics - Supplement (no supplement found)
- **other_notes:** This paper is primarily a neuroimaging comparison study testing whether social conformity and RL share neural mechanisms (they largely do not, per MVPA). The Q-learning model serves as a tool to generate trial-by-trial PE regressors for fMRI analysis rather than as a model of social learning. The paper explicitly references Lockwood, Apps, & Chang (2020) and Marr's three levels framework. The main finding is a null result — MVPA provides no evidence for a common neural mechanism between social conformity and RL, suggesting the RL hypothesis of social conformity is too simplistic.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = general
- spec_locus = source
- spec_neural = dedicated
- spec_source = partly
- spec_target = partly
- tax_domain_A_influence_transmission
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MF
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_primary_topic = norm_conformity
- tax_rr_topic_norm_conformity
- tax_topic_norm_conformity
