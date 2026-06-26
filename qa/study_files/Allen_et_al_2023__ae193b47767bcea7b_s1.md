# Allen et al. (2023)

- **study_id:** `ae193b47767bcea7b_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Allen, T. A., Hallquist, M. N., & Dombrovski, A. Y. (2023). The dark side of mentalizing: Learning signals in the default network during social exchanges support cooperation and exploitation. *bioRxiv*. https://doi.org/10.1101/2023.05.03.538867
- **citation_short:** Allen et al. (2023)
- **doi:** 10.1101/2023.05.03.538867
- **publication_type:** preprint
- **year:** 2023.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Department of Psychology and Neuroscience, University of North Carolina at Chapel Hill,; Department of Psychiatry, University of Pittsburgh, Pittsburgh, PA, 15213; lable under aCC-BY-NC-ND 4; emails: allenta@pitt.edu
- **code_url:** 

## Computational level
- **study_focus:** Reciprocal cooperation learning; how counterfactual learning signals in the default network relate to individual differences in callousness vs. exploitativeness during social exchanges.
- **study_focus_short:** Reciprocal cooperation learning
- **learning_mode_description:** - Learning mode: Learning from counterfactual and actual outcomes of social exchanges about the value of one's behavioral policy toward a social partner   - Learning from:     - Source type (social): other (trustee counterpart)     - Source content (social): outcome (trustee's decision to share/keep, including counterfactual feedback on keep trials)   - Learning about:     - Target type (social): other (trustee counterpart)     - Target content (social): action/policy (value of one's own keep/share policy toward the counterpart)
- **task_description:** In a modified iterated trust game, participants received $1.00 per trial to keep or share with one of three trustees (good, bad, neutral reputation); if participants shared, the trustee could return $1.50 or keep everything, and critically, participants saw the trustee's decision even on keep trials (counterfactual feedback). Trustees shared at varying rates (50%, 25%, or 88%) across blocks of 16 trials.
- **task_paradigm:** Trust game
- **players:** Single agent (participant), multi-target (3 trustees: good, bad, neutral reputation)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Neutral White male faces (NimStim), reputation descriptions, binary keep/share decisions, monetary outcomes ($0, $1.00, $1.50)
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Policy model dominated all alternatives in Bayesian model comparison (protected exceedance probability = 1.00, BOR < .001) - Stronger PE signals in default network predicted greater reciprocity (beta = .25, 95% CI [.09, .39], p < .001) - Callousness negatively associated with PE modulation of default network (beta = -.39, SE = .10, p < .001) - Exploitativeness positively associated with PE modulation of default network (beta = .26, SE = .10, p = .01) - Indirect effect of callousness on reciprocity via PE-DN (b = -.05, 95% CI [-.10, -.02], p < .001) - Indirect effect of exploitativeness on reciprocity via PE-DN (b = .03, 95% CI [.004, .07], p = .03) - Callousness moderated reputation effect on sharing (beta = .26, 95% CI [.04, .45], p = .01) - PE signaling in medial temporal subsystem selectively related to reputation sensitivity (beta = -.31, 95% CI [-.53, -.03], p = .04)
- **effect_size:** beta = .25 (PE-DN on reciprocity); beta = -.39 (callousness on PE-DN); beta = .26 (exploitativeness on PE-DN); b = -.05 (indirect: callousness to reciprocity via PE-DN); b = .03 (indirect: exploitativeness to reciprocity via PE-DN); beta = .62 (reciprocity behavioral effect)
- **learning_from:** Other (trustee); actual and counterfactual outcomes of trustee's share/keep decisions
- **learning_about:** Other (trustee); value of own behavioral policy (keep/share) toward each social partner  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Policy Q-learning model (1 alpha, 1 b [temperature], 1 kappa_s [general keep/share bias], 2 kappa_t [trustee-specific reputation biases: good, bad]); counterfactual payoff matrix where correctly predicting trustee defection yields positive PE.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "Actual Rewards model", "family": "Q-learning", "n_params": 5, "metric": "Random effects Bayesian model comparison (BOR)"} 2. {"name": "Regret model", "family": "Q-learning", "n_params": 5, "metric": "Random effects Bayesian model comparison (BOR)"} 3. {"name": "Counterpart Counterfactual model", "family": "Q-learning", "n_params": 5, "metric": "Random effects Bayesian model comparison (BOR)"} 4. {"name": "Policy model (winning)", "family": "Q-learning", "n_params": 5, "metric": "Random effects Bayesian model comparison (BOR)"}
- **model_mb_mf:** MF
- **model_params:** - alpha: learning rate, speed of updating keep/share values - b: temperature parameter, choice stochasticity - kappa_s: participant-level bias to keep or share regardless of reinforcement [S] - kappa_t(good): bias to keep/share with good trustee relative to neutral [S] - kappa_t(bad): bias to keep/share with bad trustee relative to neutral [S]  Mean fitted values not reported in paper.
- **social_param:** kappa_s (general social sharing bias); kappa_t(good) and kappa_t(bad) (reputation-dependent sharing biases toward good and bad trustees)
- **social_param_name:** kappa_t
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Random effects Bayesian model comparison with Bayesian Omnibus Risk (BOR) and protected exceedance probability
- **how_model_fit:** individual-level-fit (Variational Bayesian Analysis leveraging group-level priors to constrain individual estimates)
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — signed PE from policy model used as parametric modulator of feedback event; value signal as parametric modulator of choice event
- **contrast:** - Signed policy prediction error at feedback (whole-brain, pTFCE FWE p < .05) - PE modulation of default network subsystems (core, medial temporal, dorsal medial) extracted via atlas-based parcellation and factor analysis
- **key_regions:** Policy PE throughout default network (85% of posterior hub voxels); bilateral ventral/dorsal striatum, putamen, PCC/precuneus, ACC, bilateral middle/inferior temporal gyrus, lateral occipital cortex, frontal pole/medial frontal cortex. Medial temporal subsystem selectively related to reputation sensitivity.
- **key_regions_abbrev:** putamen, dStr, striatum, ACC, PCC, precuneus
- **coordinates_peak:** - Bilateral Putamen/Striatum/Hippocampus/Amygdala: -15.2, 8.1, -10.3 - Left Lateral Occipital/Inferior Temporal/Middle Temporal: -55.9, -66.9, -10.3 - Precuneus/PCC/ACC: 6.6, -45, 33.1 - Right Lateral Occipital/Inferior Temporal/Middle Temporal: 50.4, -60.6, -13.4 - Left Postcentral/Supramarginal/Precentral: -49.6, -38.8, 61 - Right Cerebellum: 37.9, -70, -41.3 - Left Cerebellum: -46.5, -73.1, -35.1 - Frontal Pole/Frontal Medial/Paracingulate: 0.4, 51.9, -10.3 - Superior Frontal/SMA/Paracingulate/ACC (negative PE): 9.8, 14.4, 70.3 - Right Superior Frontal: 25.4, 33.1, 51.7 - Right Precuneus/Lingual (negative PE): 19.1, -60.6, 8.3 - Right Insula/Frontal Operculum (negative PE): 31.6, 20.6, 8.3 - Left Frontal Operculum (negative PE): -43.4, 14.4, 5.2 - Right Postcentral/Precentral (negative PE): 47.2, -13.8, 48.6 - Right Temporal Pole (negative PE): 50.4, 8.1, -38.2 - Left Frontal Orbital (negative PE): -40.2, 20.6, -13.4 - Left Lingual (negative PE): -21.5, -51.2, 2.1  Note: These are center-of-mass coordinates, not peak coordinates. Threshold: z > 5.16, pTFCE FWER p < .05.
- **analysis_type:** whole-brain (pTFCE correction) + ROI (atlas-based default network parcels extracted for MSEM analyses) = both  ---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 168 behavioral (113 BPD, 55 healthy controls); N = 150 fMRI (after exclusions for missing data, poor quality, motion); N = 161 self-report; ages M = 31.16 (SD = 9.30); 78% female
- **population_category:** healthy adults
- **population_age_range:** M=31.16 (SD=9.30)
- **ecological_validity:** Modified trust game with counterbalanced reputation manipulation provides reasonable social interaction structure, though trustees are fictional (photographs + descriptions) rather than real interaction partners. Counterfactual feedback display is somewhat artificial. Clinical sample (BPD + healthy) provides naturalistic personality variation.
- **eligibility_flag:** 
- **concerns:** - Mean fitted parameter values not reported for the winning model - Coordinates reported are center-of-mass, not peak voxel coordinates - Cross-sectional design precludes causal inference - Clinical sample (BPD + healthy) pooled; group differences not modeled - Parameter recovery and model recovery analyses referenced from prior publication (Vanyukov et al., 2019) rather than performed in this study - Preprint, not peer-reviewed
- **limitations_reported:** Our observations were cross-sectional in nature and contingent on the naturalistic manipulation of human individual differences, precluding strong causal inferences.
- **limitations_categorized:** cross-sectional design; limited causal inference; naturalistic individual differences manipulation
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
- **wc_rule10:** Partial
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** unclear
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_params mean fitted values: LOW — not reported in paper or supplement - coordinates_peak: MEDIUM — center-of-mass coordinates reported, not peak voxel - WC rules 3, 5, 6: MEDIUM — referenced from Vanyukov et al. (2019), not performed in current study - limitations_reported: MEDIUM — only one sentence in discussion; may be additional limitations not explicitly labeled
- **cannot_find:** - Mean fitted parameter values for the winning model - Peak voxel coordinates (only center-of-mass reported) - Data/code sharing statement - Preregistration status
- **other_notes:** This paper builds directly on Vanyukov et al. (2019), which originally developed and validated the policy model. The current paper's primary contribution is linking the model's PE signals in the default network to individual differences in callousness and exploitativeness using multilevel SEM. The sample is a clinical/community sample enriched for BPD, providing wide personality variation. Some participants (n=58) also interacted with a "computer" trustee whose data were excluded. The Bayesian MSEM approach is methodologically sophisticated, enabling cross-level mediation testing.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_bpd
- pop_healthy_adults
- rr_pop_bpd
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_neural = shared
- spec_source = social
- spec_target = social
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_instructed
- tax_mod_mentalizing_inference
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = reciprocity
- tax_rr_secondary_topic = trust
- tax_rr_topic_reciprocity
- tax_rr_topic_trust
- tax_topic_reciprocity
- tax_topic_trust
