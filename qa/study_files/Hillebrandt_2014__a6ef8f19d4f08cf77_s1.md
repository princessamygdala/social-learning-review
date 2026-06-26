# Hillebrandt (2014)

- **study_id:** `a6ef8f19d4f08cf77_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Hillebrandt, H. F. (2014). *Bayesian hierarchical predictive coding of human social behaviour* [Doctoral dissertation, University College London]. Institute of Cognitive Neuroscience, University College London.
- **citation_short:** Hillebrandt (2014)
- **doi:** Not available (PhD thesis; individual chapters published separately with DOIs listed in the contributions section).
- **publication_type:** thesis
- **year:** 2014.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** laborator and unofficial supervisor who taught me a lot about research, Joshua Greene, my; ether, but no one person knows how to build the oil rig to extract the; lab at Harvard, and my PhD cohorts at UCL and Harvard, especially, P; labour of billions of people who make modern research possible –; University College London in form of a scholarship, and the; lab at the Institute of Cognitive Neuroscience,; INSTITUTE OF COGNITIVE NEUROSCIENCE; UCL and Harvard, especially to
- **code_url:** https://github.com/HaukeHillebrandt/SPM_connectome

## Computational level
- **study_focus:** The overarching theme is social cognition examined through the lens of predictive coding theory: perspective-taking, trust after inclusion/exclusion, and animacy perception.
- **study_focus_short:** The overarching theme is social cognition examined through the lens of
- **learning_mode_description:** Not applicable -- no learning over time occurs in any study.  ---  ## (6) Computational Problem  Not applicable -- no computational problem of learning is formalized.  ---  ## (7) Results with ES
- **task_description:** 
- **task_paradigm:** Perspective-taking / trust tasks (thesis)
- **players:** 
- **n_players:** 
- **partner_type:** none
- **stimuli:** 
- **method:** other
- **main_result:** 
- **effect_size:** 
- **learning_from:** 
- **learning_about:** 
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** Not applicable in the learning-model sense. The "winning model" in Chapters 4-5 is the full DCM model (all connections modulated), selected via post-hoc Bayesian model selection. This is a neural connectivity model, not a learning model.  ---  ## (9) All Models Tested
- **model_family:** Bayesian
- **model_class:** Other
- **all_models_tested:** 
- **model_mb_mf:** 
- **model_params:** 
- **social_param:** 
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** 
- **how_model_fit:** 
- **data_type_fit_to:** 

## Implementation level
- **fmri_model_type:** Chapter 3: univariate GLM; Chapter 4: DCM; Chapter 5: DCM
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** 
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** - Chapter 2: N=24 females (12 Reputation, 12 No Reputation); ages ~20-21 - Chapter 3: N=28 (14 adults aged 21-30, 14 adolescents aged 11-16), all female - Chapter 4: N=11 adults (subset of Ch.3), all female - Chapter 5: N=132 (89 female, 43 male), HCP data, ages ~22-35
- **population_category:** mixed
- **population_age_range:** 21–30
- **ecological_validity:** Chapter 2 uses a relatively ecologically valid paradigm (Cyberball followed by trust game with reputation manipulation). Chapters 3-4 use a computerized Director task that attempts ecological validity through perspective-taking in a communicative context, though still artificial. Chapter 5 uses abstract triangle animations, which are low in ecological validity.
- **eligibility_flag:** Does not meet inclusion criteria. None of the four studies uses computational modeling of learning. The dissertation uses DCM (a neuroimaging connectivity method) and standard GLM, but no computational models of learning are fitted to behavioral data. There is no learning over time in any study -- Chapter 2 is a 3-round trust game without model-fitting, Chapters 3-4 use a perspective-taking task with no trial-by-trial learning, and Chapter 5 uses passive viewing of animated triangles. The "Bayesian hierarchical predictive coding" in the title refers to a theoretical interpretive framework (Friston's free energy principle), not to a computational model fitted to data.  Specific violations: - **No computational modeling** (fails criterion 1) - **No learning over time** (fails criterion 4) -- all tasks are either one-shot or block designs without trial-by-trial updating
- **concerns:** - No computational modeling of learning is present anywhere in the dissertation - The predictive coding framework is invoked as a post-hoc interpretive lens, not as a fitted model - DCM is a connectivity method, not a model of behavioral learning - Chapter 2 has small N (12 per group) and only female participants - Chapters 3-4 have small N (14 per age group) and only female participants - Chapter 4 lost 3 participants from VOI extraction, leaving only N=11  ---  ## (15) WC Checklist  Not applicable -- no computational model of learning is fitted.
- **limitations_reported:** 
- **limitations_categorized:** 
- **preregistered:** No
- **wc_rule1:** 
- **wc_rule2:** 
- **wc_rule3:** 
- **wc_rule4:** 
- **wc_rule5:** 
- **wc_rule6:** 
- **wc_rule7:** 
- **wc_rule8:** 
- **wc_rule9:** 
- **wc_rule10:** 
- **wc_score:** 0
- **wc_total:** 0.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_healthy_adults
- rr_pop_adolescents
- rr_pop_healthy_adults
- rr_tax_mod_instructed
- rr_tax_mod_mentalizing_inference
- spec_locus = target
- tax_domain_B_inference_modelling_others
- tax_domain_C_exchange_interdependence
- tax_mod_instructed
- tax_mod_mentalizing_inference
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_primary_topic = mentalizing
- tax_rr_secondary_topic = trust
- tax_rr_topic_mentalizing
- tax_rr_topic_trust
- tax_topic_mentalizing
- tax_topic_trust
