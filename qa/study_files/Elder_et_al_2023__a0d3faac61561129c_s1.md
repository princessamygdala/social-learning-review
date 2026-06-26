# Elder et al. (2023)

- **study_id:** `a0d3faac61561129c_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Elder, J. J., Davis, T. H., & Hughes, B. L. (2023). A fluid self-concept: How the brain maintains coherence and positivity across an interconnected self-concept while incorporating social feedback. *The Journal of Neuroscience, 43*(22), 4110–4128.
- **citation_short:** Elder et al. (2023)
- **doi:** 10.1523/JNEUROSCI.1951-22.2023
- **publication_type:** peer-reviewed journal---
- **year:** 2023.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofPsychology,UniversityofCalifornia,Riverside,Riverside,California92521and2Independentresearcher,Fremont,California; ethatmaintainingapositiveandcoherentself-conceptplaysinpromotingmentalhealthanddevelopmentthroughoutthe; ethroughinteractionswithothersandtheir; etheirbeliefsfromfeedbackwhenthefeed-; ethepaper; etherthe; emails: CorrespondenceshouldbeaddressedtoBrentHughesatbhughes@ucr.edu
- **code_url:** https://osf.io/2v7jc/

## Computational level
- **study_focus:** Self-concept updating from social feedback; how semantic dependency relations among traits constrain self-belief updating to maintain positivity and coherence.
- **study_focus_short:** Self-concept updating from social feedback
- **learning_mode_description:** - Learning mode: Learning from others' evaluative feedback about the self to update self-beliefs, constrained by network dependency structure among traits.   - Learning from:     - Source type (social): other (admissions committee members)     - Source content (social): outcomes (evaluative feedback on personality traits)   - Learning about:     - Target type (social): self     - Target content (social): state (mental state; self-concept / trait self-evaluations)
- **task_description:** Participants evaluated themselves on 148 positive personality traits on a 1–7 scale, then received ostensible evaluative feedback from a university admissions committee on each trait; after receiving feedback on all traits, they re-evaluated themselves on all traits without feedback. Feedback was pseudorandomly administered with different probabilities of positive feedback assigned to each of five trait-network communities.
- **task_paradigm:** Self-evaluation / self-esteem task
- **players:** Single agent (participant), multi-source (3–5 admissions committee members, fictitious)
- **n_players:** single agent (1)
- **partner_type:** none
- **stimuli:** 148 positive personality trait words, numeric Likert feedback (1–7), numeric discrepancy display
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Model-generated social expectations (SE) predicted trial-by-trial self-evaluations in leave-one-out cross-validation (b = 0.104, SE = 0.021, t(50) = 5.015, p < .001, sr² = 0.013) - SE predicted re-evaluation change (b = 0.227, SE = 0.017, t(51) = 13.044, p < .001, sr² = 0.081) - PE predicted re-evaluation change (b = 0.108, SE = 0.020, t(45) = 5.450, p < .001, sr² = 0.024) - PE x outdegree centrality interaction on re-evaluation change (b = -0.035, SE = 0.009, t(149) = -3.830, p < .001, sr² = 0.003) - Learning rate for positive PEs > negative PEs (M_pos = 0.354, M_neg = 0.080, observed difference = 0.274, p < .001) - Absolute PEs decreased over trials (r(146) = -0.168, p = .042) - vmPFC cluster for Feedback x Outdegree interaction (-6, 40, -14; k = 28, t = 3.54, p = .041) - vmPFC cluster for outdegree-dependent resistance to change (-2, 46, -16; k = 41, t = 3.35, p = .028) - vmPFC negatively associated with familiarity (2, 30, -22; k = 638, t = 5.88, p = .009) - Bilateral angular gyrus negatively associated with uncertainty (R: 60, -50, 42; k = 828, t = 6.38, p = .004; L: -58, -48, 46; k = 297, t = 4.94, p = .024) - dmPFC/pre-SMA and IFG associated with positive > negative change in self-evaluations
- **effect_size:** - Model-generated social expectations (SE) predicted trial-by-trial self-evaluations in leave-one-out cross-validation (b = 0.104, SE = 0.021, t(50) = 5.015, p < .001, sr² = 0.013) - SE predicted re-evaluation change (b = 0.227, SE = 0.017, t(51) = 13.044, p < .001, sr² = 0.081) - PE predicted re-evaluation change (b = 0.108, SE = 0.020, t(45) = 5.450, p < .001, sr² = 0.024) - PE x outdegree centrality interaction on re-evaluation change (b = -0.035, SE = 0.009, t(149) = -3.830, p < .001, sr² = 0.003) - Learning rate for positive PEs > negative PEs (M_pos = 0.354, M_neg = 0.080, observed difference = 0.274, p < .001) - Absolute PEs decreased over trials (r(146) = -0.168, p = .042) - vmPFC cluster for Feedback x Outdegree interaction (-6, 40, -14; k = 28, t = 3.54, p = .041) - vmPFC cluster for outdegree-dependent resistance to change (-2, 46, -16; k = 41, t = 3.35, p = .028) - vmPFC negatively associated with familiarity (2, 30, -22; k = 638, t = 5.88, p = .009) - Bilateral angular gyrus negatively associated with uncertainty (R: 60, -50, 42; k = 828, t = 6.38, p = .004; L: -58, -48, 46; k = 297, t = 4.94, p = .024) - dmPFC/pre-SMA and IFG associated with positive > negative change in self-evaluations
- **learning_from:** Other (admissions committee); evaluative social feedback on personality traits
- **learning_about:** Self; self-concept trait evaluations (self-beliefs about personality traits)---  ## ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** Mixture back-propagation RL model (3 params: α_pos, α_neg, ω); asymmetric learning rates with back-propagation of PEs through trait dependency network + similarity-based retrieval mixture. SE = RLSE × ω + SimSE × (1 − ω).
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "Base RL", "family": "Rescorla-Wagner", "n_params": 1, "metric": "AIC = 5711.318"} 2. {"name": "Asymmetrical learning", "family": "Rescorla-Wagner (asymmetric)", "n_params": 2, "metric": "AIC = 4938.931"} 3. {"name": "Overall propagation", "family": "RL + network propagation (all paths)", "n_params": 2, "metric": "AIC = 4389.841"} 4. {"name": "Forward propagation", "family": "RL + network propagation (outdegree paths)", "n_params": 2, "metric": "AIC = 4409.306"} 5. {"name": "Back-propagation", "family": "RL + network propagation (indegree paths)", "n_params": 2, "metric": "AIC = 4386.371"} 6. {"name": "Mixture with similarity (back-propagation)", "family": "RL + network propagation + similarity retrieval", "n_params": 3, "metric": "AIC = 4355.706"}
- **model_mb_mf:** MF (model-free RL with structured state space)
- **model_params:** - α_pos [S]: positive learning rate (mean = 0.354, median = 0.136, SD = 0.403) — rate of updating from positive PEs (feedback better than expected) - α_neg [S]: negative learning rate (mean = 0.080, median = 0.039, SD = 0.102) — rate of updating from negative PEs (feedback worse than expected) - ω: mixture parameter — weight on RL-based expectations (RLSE) vs. similarity-based expectations (SimSE); closer to 1 = more reliance on trial-and-error, closer to 0 = more reliance on similarity retrieval
- **social_param:** α_pos and α_neg [S] — asymmetric learning rates for positive vs. negative social feedback prediction errors; the asymmetry (α_pos > α_neg) reflects a positivity bias in self-concept updating from social feedback. Network propagation mechanism is also inherently social (propagation through trait dependency network reflects social self-concept structure).
- **social_param_name:** α_pos
- **social_param_value:** 0.354
- **social_param_sd:** 0.403
- **social_param_range:** 
- **model_comparison_metric:** AIC (summed across subjects); BIC also reported
- **how_model_fit:** Individual-level fit using L-BFGS-B optimization (least squares); group-level parameters (mean learning rates, median mixture) used for fMRI regressors
- **data_type_fit_to:** Choice behavior (self-evaluation ratings on 1–7 Likert scale)---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors derived from RL model: PE, RLSE, familiarity, uncertainty)
- **contrast:** - PE (overall prediction error at feedback onset) - PE conjunction: PE ∩ (Feedback > RLSE) — justifying PE vs. mere feedback - Positive PE > Negative PE - Negative PE > Positive PE - Feedback × Outdegree centrality (ROI: vmPFC) - PE × Outdegree centrality (ROI: vmPFC) - Positive change > Negative change (in self-evaluations) - No Change × Outdegree centrality (whole-brain + vmPFC ROI) - Familiarity (at self-evaluation onset) - Uncertainty/entropy (at self-evaluation onset)
- **key_regions:** PE conjunction in vmPFC (0, 40, -24) and PCC (0, -44, 4); positive > negative PE in vmPFC (0, 34, -22), bilateral STS, precuneus, PCC, bilateral OFC, dmPFC; negative > positive PE in bilateral insula, somatosensory cortex; Feedback × Outdegree interaction in vmPFC ROI (-6, 40, -14); outdegree-dependent resistance to change in vmPFC ROI (-2, 46, -16), dmPFC/pre-SMA (0, 16, 42), left IFG (-52, 8, 40); familiarity (novelty) in vmPFC (2, 30, -22), posterior MTG (-50, -30, -4), right MFG (44, 6, 32); uncertainty (certainty) in bilateral angular gyrus (R: 60, -50, 42; L: -58, -48, 46).
- **key_regions_abbrev:** vmPFC, mPFC, dmPFC, OFC, PCC, STS, insula, AI, precuneus, IFG
- **coordinates_peak:** PE conjunction — vmPFC: 0, 40, -24 PE conjunction — PCC: -2, -44, 4 PE — Lingual gyrus: -14, -78, 8 PE — Bilateral accumbens/putamen: -14, 0, -14 Positive PE > Negative PE — Left lateral OFC: -48, 22, -8 Positive PE > Negative PE — Superior frontal gyrus: 0, 54, 26 Positive PE > Negative PE — Right lateral OFC: 46, 22, -10 Positive PE > Negative PE — vmPFC: 0, 34, -22 Negative PE > Positive PE — Postcentral gyrus/R somatosensory: 64, -30, 44 Feedback × Outdegree — vmPFC (ROI): -6, 40, -14 No Change × Outdegree — vmPFC (ROI): -2, 46, -16 No Change × Outdegree — dmPFC/pre-SMA: 0, 16, 42 No Change × Outdegree — Left IFG: -52, 8, 40 Positive Change > Negative Change — Left MFG: -34, -2, 66 Positive Change > Negative Change — dmPFC/pre-SMA: 0, 32, 42 Familiarity (negative) — vmPFC: 2, 30, -22 Familiarity (negative) — Left posterior MTG: -50, -30, -4 Familiarity (negative) — Right MFG: 44, 6, 32 Uncertainty (negative) — Right angular gyrus: 60, -50, 42 Uncertainty (negative) — Left angular gyrus: -58, -48, 46 Uncertainty (negative) — Right superior parietal lobule: 34, -42, 40
- **analysis_type:** Both (whole-brain for most contrasts; ROI for vmPFC-specific Feedback × Outdegree and No Change × Outdegree analyses)---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 46 (63.0% female; ages 18–31, M = 19.89); 2 subjects had incomplete self-report questionnaires due to protocol errors. Trait dependency network constructed from independent sample of N = 178 Amazon Mechanical Turk participants.
- **population_category:** healthy adults
- **population_age_range:** 18–31
- **ecological_validity:** Moderate. The task uses deception (fictitious admissions committee feedback), which enhances realism relative to computer-generated feedback, but is still a lab-based paradigm with trait-word stimuli rather than naturalistic social interaction. Only positive traits were included, limiting generalizability to negative self-concept domains. Feedback was pseudorandomly generated, not based on actual evaluations.
- **eligibility_flag:** 
- **concerns:** (1) Only positive traits were used — generalizability to negative trait updating unknown. (2) Feedback described as coming from admissions committee members, raising questions about generalizability to other social sources. (3) A coding error changed community detection from 5 to 4 communities after data collection, though the original 5-community structure was used for feedback administration. (4) vmPFC Feedback × Outdegree and resistance-to-change interactions were ROI analyses with liberal thresholding (p < .01 cluster-forming), raising specificity concerns. (5) The PE × Outdegree interaction in vmPFC was only marginally significant (p = .058). (6) Preregistration existed but analyses shifted substantially from what was preregistered. [HIGH]
- **limitations_reported:** We made a number of pragmatic choices when designing this task that open new avenues for future research. First, we constructed two discrete networks, one containing positive traits and another containing negative traits, and focused here on the positive trait network, given our interest to examine how feedback propagates to all traits within a network. Including both complete networks would not have been possible because of time constraints and participant fatigue. Future research can test whether the current mechanisms extend to learning about negative traits."; "We also described feedback to participants as coming from admissions committee members. This raises interesting questions about whether learning effects vary based on status or other features of the sources of feedback."; "Future studies might also compare how people learn about themselves and others to examine the differences between self-relevant relative to other-relevant learning."
- **limitations_categorized:** Limited ecological validity (positive traits only); task simplicity (single feedback source type); limited generalizability (self-relevant learning only, no comparison to other-relevant); time constraints limiting design scope; deviation from preregistration
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 9
- **wc_total:** 9.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_mb_mf: MEDIUM — classified as MF because the core learning is RL/Rescorla-Wagner (error-driven), but the network propagation mechanism introduces structure that could be considered model-based - WC Rule 6 (model recovery): No confusion matrix or model recovery simulation reported; only parameter recovery was tested
- **cannot_find:** - No supplement was available or found for this paper - No model recovery/confusion matrix reported - BIC for the winning model (mixture with similarity) showed worse fit than back-propagation alone (BIC = 4761.537 vs. 4656.925), but authors chose AIC as primary criterion
- **other_notes:** This paper builds directly on Elder et al. (2022, Psychological Science) which used the same task design behaviorally. The trait dependency network was constructed from an independent sample (N = 178 MTurk). The back-propagation finding (errors propagate to parent traits rather than child traits) is a distinctive theoretical contribution. The mixture parameter ω capturing reliance on trial-and-error vs. similarity-based retrieval is conceptually interesting for the social learning literature. Preregistration at AsPredicted exists but deviations are acknowledged.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_social_weight
- tax_param_valence_asymmetry
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = self_esteem
- tax_rr_secondary_topic = social_approval_reward
- tax_rr_topic_self_esteem
- tax_rr_topic_social_approval_reward
- tax_topic_self_esteem
- tax_topic_social_approval_reward
