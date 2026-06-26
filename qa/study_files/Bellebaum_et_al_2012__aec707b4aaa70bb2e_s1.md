# Bellebaum et al. (2012)

- **study_id:** `aec707b4aaa70bb2e_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Bellebaum, C., Jokisch, D., Gizewski, E. R., Forsting, M., & Daum, I. (2012). The neural coding of expected and unexpected monetary performance outcomes: Dissociations between active and observational learning. *Behavioural Brain Research*, *227*(1), 241-251.
- **citation_short:** Bellebaum et al. (2012)
- **doi:** 10.1016/j.bbr.2011.10.042
- **publication_type:** peer-reviewed journal
- **year:** 2012.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** University Hospital Essen, Department of Diagnostic and Interventional Radiology and Neuroradiology, Essen, Germany; Institute of Cognitive Neuroscience, Department of Neuropsychology, Ruhr University Bochum, Germany; ucleus and in the medial orbitofrontal cortex were stronger for active; University Hospital Essen, Department of Neurology, Essen, Germany; University, UKGM, Department of Neuroradiology, Giessen, Germany; ether or not subjects have to perform a response to receive; Department of Neuropsychology, Ruhr University; lable at SciVerse ScienceDirect; emails: christian.bellebaum@rub.de
- **code_url:** 

## Computational level
- **study_focus:** Observational learning; active vs. observational reward prediction error coding
- **study_focus_short:** Observational learning; active vs. observational reward prediction error coding
- **learning_mode_description:** - Learning mode: Learning from monetary feedback outcomes about stimulus-outcome values via active choices or observation of another's choices   - Learning from:     - Source type (non-social in active condition; social in observational condition): self (active learners) / other (observed person, in observational learners)     - Source content (non-social): outcomes (monetary reward/non-reward/punishment)   - Learning about:     - Target type (non-social): world (stimulus-outcome contingencies)     - Target content (non-social): stimulus (abstract symbol reward values)
- **task_description:** Participants either actively chose between pairs of abstract symbols (Hiragana characters) and received monetary feedback (+20c, 0c, or -20c) with probabilistic contingencies, or observed a yoked active learner's choices and outcomes. Both groups were tested via active test trials without feedback after each block.
- **task_paradigm:** Observational learning task
- **players:** Multi-agent (dyad, yoked observer-actor), between-subjects design (N=15 active learners, N=15 observational learners)
- **n_players:** network (5+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract Hiragana characters (4 symbols: A, B, C, D); monetary outcomes (+20 Cent, 0 Cent, -20 Cent); hand symbol and red circle for observed choices
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Active learners showed increased right putamen activity for unexpected vs. expected reward (Z = 4.13) and decreased left hippocampus activity - Observational learners showed increased left hippocampus activity for unexpected vs. expected reward (Z = 3.95) - Between-group comparison: bilateral hippocampus showed enhanced activity for unexpected reward in observers vs. active learners (left: Z = 4.45; right: Z = 3.83) - PE parametric modulation: right putamen active in both groups (conjunction); bilateral basal ganglia and medial OFC active only in active learners - Stronger PE modulation in active vs. observational learners in right anterior caudate nucleus (Z = 3.48) and bilateral medial OFC (Z = 4.47) - Behavioural learning comparable between groups; no significant group difference in test trial accuracy (p = .074 trend)
- **effect_size:** - Active learning block effect: F(1,13) = 49.873 (linear trend) - Test trial PAIR main effect: F(1.507, 39.194) = 5.915 - AB vs CD test accuracy: t(27) = 2.630 - BC vs CD test accuracy: t(27) = 2.407 - Between-group conjunction right putamen PE: Z = 3.50 - Active learners right putamen unexpected reward: Z = 4.13 - Observational learners left hippocampus unexpected reward: Z = 3.95 - Between-group left hippocampus: Z = 4.45 - Between-group right hippocampus: Z = 3.83 - Active PE medial OFC: Z = 4.32 - Active > observational PE medial OFC: Z = 4.47 - Active > observational PE right anterior caudate: Z = 3.48
- **learning_from:** Other (observed person's choices and outcomes) in observational condition; self (own choices and outcomes) in active condition. Source: monetary feedback outcomes.
- **learning_about:** World; stimulus-outcome value associations (which abstract symbols yield best monetary outcomes)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Simple Rescorla-Wagner: Q(t+1) = Q(t) + alpha * delta(t), where delta(t) = outcome(t) - Q(t). Individual alpha fitted per subject, per stimulus, per block using known subjective values from test trial performance. Not a freely estimated model -- alpha was derived deterministically to match known start and end values.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Simple RL model (RW)", "family": "Rescorla-Wagner", "n_params": 1, "metric": "N/A - deterministic fit to known values"}]
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate): individually determined per subject, per stimulus, per block to fit known subjective values at block boundaries. No group mean reported. - Q(t): subjective value of stimulus, initialized at 0 Cent - delta(t): prediction error = outcome(t) - Q(t)
- **social_param:** None explicitly. The same model was applied to both active and observational learners; the social manipulation was between-subjects (active vs. observational group), not parameterized within the model.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** N/A -- only one model applied; no formal model comparison conducted.
- **how_model_fit:** params-calculated-independently (alpha was deterministically derived to match known subjective values at block start and end points based on test trial performance, not freely estimated via MLE or Bayesian fitting)
- **data_type_fit_to:** choice behavior (test trial performance used to derive subjective values)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** univariate GLM + model-based fMRI (parametric regressors for PE magnitude)
- **contrast:** - Unexpected > expected reward (active learners; observational learners; between-group) - Unexpected < expected non-reward (active learners; observational learners; between-group) - PE parametric modulation (conjunction; per group; between-group)
- **key_regions:** PE modulation shared in right putamen for both groups; active-specific PE coding in bilateral striatum (putamen + caudate) and medial OFC; observational-specific unexpected reward coding in bilateral hippocampus; active > observational PE in right anterior caudate and medial OFC.
- **key_regions_abbrev:** caudate, putamen, striatum, OFC, hippocampus
- **coordinates_peak:** Unexpected > expected reward, active: right putamen: 28, 6, 4; left hippocampus (reduced): -22, -26, -18; medial OFC (reduced): -2, 48, -14; orbital gyrus (reduced): 0, 44, -22; ACC (reduced): -6, 48, 12 Unexpected > expected reward, observational: left hippocampus: -30, -26, -12 Between-group reward (obs > active): left hippocampus: -24, -30, -22; right hippocampus: 32, -16, -14 Between-group reward (active > obs): right putamen: 28, 4, 4 (p < .005) Unexpected < expected non-reward, active: right putamen: 28, -4, -2; left hippocampus: -30, -14, -24; medial OFC: 6, 44, -14; ACC: -8, 42, 2 Unexpected < expected non-reward, observational: left putamen: -22, 10, 2; medial OFC: 0, 56, -18; medial OFC/ACC: 14, 40, -6 Between-group non-reward (active > obs): right putamen: 24, 10, 18; medial OFC: -24, -30, -22 PE conjunction: right putamen: 26, 6, -4 PE active learners: medial OFC: 6, 46, -14; bilateral basal ganglia (see Table S5 for local peaks) PE observational: right putamen: 24, 14, -4 PE active > observational: medial OFC (medial frontal gyrus): 6, 46, -14; medial OFC (rectal gyrus): 0, 40, -22; right anterior caudate: 14, 18, -4
- **analysis_type:** both (whole-brain at p < .001 uncorrected + small volume correction with 10mm spheres around a priori ROIs)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N=30 (15 active learners: 9 women, mean age 26.0, SD=4.1; 15 observational learners: 10 women, mean age 26.2, SD=4.9)
- **population_category:** healthy adults
- **population_age_range:** M=26.0
- **ecological_validity:** Low-moderate; abstract stimulus-reward learning with monetary outcomes; observational learning is of a yoked partner's recorded choices rather than live social interaction; no face-to-face or real-time social component.
- **eligibility_flag:** 
- **concerns:** Small sample size (N=15 per group); between-subjects design limits within-subject comparison power; the RL model is not freely fitted -- alpha is deterministically derived from test trial performance, which is an unusual fitting approach; no formal model comparison; threshold of p < .001 uncorrected is liberal by modern standards; supplementary tables S1-S5 not accessible (published online only); PE parametric modulator conflates reward valence with PE magnitude to some extent (authors acknowledge this). The "social" aspect is observing a recorded partner's choices, not live interaction.
- **limitations_reported:** Cannot exclude that subjective reward value differed between active and observational learners despite instruction matching; no clear results for neural structures specifically recruited during observational outcome coding; differences from Burke et al. (2011) may relate to within- vs. between-subjects design differences; the PE analysis was partly influenced by the physical difference between reward and non-reward stimuli; the differential role of the hippocampus in active and observational learning requires further exploration.
- **limitations_categorized:** potential reward value confound; between-subjects design; limited ecological validity; sample size; incomplete characterization of observational learning mechanisms
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Partial
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** No
- **wc_score:** 2.5
- **wc_total:** 2.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params (MEDIUM): alpha values not reported as group means; derived per subject/stimulus/block - social_param (HIGH): no explicit social parameter in the model; social manipulation is between-subjects - coordinates_peak (MEDIUM): supplementary Tables S1-S5 referenced but not accessible; coordinates extracted from figure captions and main text only - effect_size (MEDIUM): Z-scores from fMRI contrasts reported; no standardized behavioral effect sizes (Cohen's d, eta-squared) beyond F-statistics - winning_model (MEDIUM): described as "simple reinforcement learning model" but fitting approach is non-standard (deterministic derivation)
- **cannot_find:** Supplementary Tables S1-S5 (complete activation lists); mean fitted alpha values; formal model comparison statistics; standardized effect sizes for behavioral group differences
- **other_notes:** This paper uses a between-subjects design comparing active and observational learning groups. The RL model is applied to generate trial-by-trial PE estimates for fMRI analysis, not as a cognitive model to be formally compared. The approach of deriving alpha from test trial performance (matching known start/end subjective values) is unusual and deterministic rather than freely estimated. The social aspect is limited -- observational learners watch recorded choices of a yoked active learner, not a live partner.
- **re_extract_flag:** false (full text read; supplement not accessible but noted)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = general
- spec_locus = source+target
- spec_neural = shared
- spec_source = social
- tax_domain_B_inference_modelling_others
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = imitation_emulation
- tax_rr_topic_imitation_emulation
- tax_topic_imitation_emulation
