# Gadeke et al. (2020)

- **study_id:** `aad2e89eeb949f588_s2`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Gadeke, M., Willems, T., Ahmed, O. S., Weber, B., Hurlemann, R., & Schultz, J. (2020). A neural mechanism of social responsibility. *bioRxiv*. https://doi.org/10.1101/2020.05.25.107300
- **citation_short:** Gadeke et al. (2020)
- **doi:** 10.1101/2020.05.25.107300
- **publication_type:** preprint
- **year:** 2020.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Institute of Experimental Epileptology and Cognition Research, Medical Faculty,; Center for Economics and Neuroscience, University of Bonn, Bonn, Germany; Department of Psychiatry, University of Oldenburg, Oldenburg, Germany; Institute of Psychology, University of Bern, Bern, Switzerland; University of Bonn, Bonn, Germany; ether one should go to war; lable under aCC-BY-NC-ND 4; emails: johannes.schultz@ukbonn.de
- **code_url:** 

## Computational level
- **study_focus:** Same as Study 1 -- social responsibility learning, now with neuroimaging.
- **study_focus_short:** Same as Study 1 -- social responsibility learning, now with neuroimaging
- **learning_mode_description:** Same as Study 1.
- **task_description:** Same gambling task as Study 1 performed inside fMRI scanner (2 sessions instead of 3; longer ISIs for fMRI). Participants chose between safe and risky options affecting self and/or partner, rated happiness every two trials.
- **task_paradigm:** Risky decision-making
- **players:** Single agent (participant), dyadic (confederate partner; authors TW and MG served as confederates; partner choices simulated)
- **n_players:** dyadic (2)
- **partner_type:** confederate
- **stimuli:** Monetary gamble options (safe vs. risky), happiness rating scale
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Behavioural replication: responsibility effect on happiness confirmed (d = 0.34, BF10 = 8.8 for self-win/partner-lost; d = 0.48, BF10 = 1.3 for self-lost/partner-lost) - Responsibility model: highest R² = 0.435; Responsibility Redux: best BIC (-664) and AIC (-1082) - self_pRPE weight > 0 (Z = 3.64, p = 0.0003); partner_pRPE not significant (Z = 0.85, p = 0.40) - Left anterior insula: larger activation for negative outcomes from own vs. partner's choices (F(1,39) = 4.98, p = 0.03) - Left STS cluster (MNI: -52, -32, 0; Z = 4.6): higher BOLD response to partner RPEs from participant's vs. partner's choices - Bilateral ventral striatum more active for risky vs. safe choices (Right: x=10, y=12, z=-2, Z=4.56; Left: x=-12, y=10, z=-8, Z=4.37)
- **effect_size:** See above.
- **learning_from:** Self and other (partner); monetary outcomes / reward prediction errors from risky choices
- **learning_about:** Same as Study 1  ---  #### ALGORITHMIC LEVEL (Study 2)  Same models tested and same structure as Study 1.
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Responsibility Redux (best BIC/AIC); Responsibility model (best R²). Same formula as Study 1.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** Same 6 models as Study 1.
- **model_mb_mf:** MF
- **model_params:** Same as Study 1. Forgetting factor gamma range 0.42-0.46 in Study 2.
- **social_param:** Same as Study 1.
- **social_param_name:** Same as Study 1.
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 0.42–0.46
- **model_comparison_metric:** R², adjusted R², BIC, AIC (summed across 40 subjects), repeated-measures ANOVA.
- **how_model_fit:** individual-level-fit
- **data_type_fit_to:** self-report ratings (momentary happiness); also neural activity (model-based fMRI with computational regressors from Responsibility model)  ---  #### IMPLEMENTATION LEVEL (Study 2)

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors from fitted Responsibility RL model) + univariate GLM (standard contrasts)
- **contrast:** - Risky > safe choice: bilateral ventral striatum - Partner chose > participant chose (social conditions): STS, lateral/medial PFC, OFC - Participant chose > partner chose: bilateral lingual gyrus, cuneus, caudate, STG, PFC - Risky outcome > safe outcome: mPFC, bilateral AI, bilateral dlPFC, bilateral IPS, right STS, bilateral VS - Negative PE x self-decided (interaction): left anterior insula - self_pRPE > partner_pRPE (computational regressor contrast): left STS
- **key_regions:** Social responsibility (negative outcomes from own choices) in left anterior insula; partner RPE modulated by responsibility in left STS; risky choice selection in bilateral ventral striatum.
- **key_regions_abbrev:** VS, striatum, STS, insula, AI
- **coordinates_peak:** - Right ventral striatum (risky > safe choice): 10, 12, -2 - Left ventral striatum (risky > safe choice): -12, 10, -8 - Left superior temporal sulcus (self_pRPE > partner_pRPE): -52, -32, 0  Note: Left anterior insula coordinates not explicitly reported as a peak -- it was identified from within the risky > safe outcome contrast mask. Other contrasts (partner > self choose, self > partner choose) list regions but not peak coordinates in text.
- **analysis_type:** both (whole-brain analysis with cluster-level FWE correction at p < 0.05, based on voxelwise p < 0.001 uncorrected; computational model analysis constrained by inclusive mask from risky > safe outcome contrast)  ---  #### PAPER QUALITY (Study 2)
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 44 (19 male, mean age 30.6 SD 6.5, range 23-50); 4 excluded from fMRI for excess motion, so N = 40 for imaging analyses
- **population_category:** healthy adults
- **population_age_range:** 23–50
- **ecological_validity:** Same as Study 1. Addition of fMRI scanner environment further reduces ecological validity.
- **eligibility_flag:** Borderline. The models do not represent traditional "learning over time" -- there is no learning rate or belief updating. The model is a weighted regression of momentary happiness on recent reward history with exponential decay. This is closer to a descriptive affective model than a learning model. Flag as: "borderline learning-vs-decision-making; model captures temporal dynamics of happiness via exponential decay but no explicit learning rate or belief updating mechanism.
- **concerns:** Same as Study 1, plus: confederate partners were the authors (TW and MG) in Study 2, introducing potential demand characteristics. Anterior insula finding is from a post-hoc ROI analysis within outcome-responsive regions (not independently defined). Partner choices always followed highest-EV algorithm. 4 participants excluded for motion. The model is not a standard learning model -- it models happiness as a weighted sum of recent events, not updating of value estimates.
- **limitations_reported:** Same as Study 1 (limitations are discussed for both studies together). Additionally: different neural correlates identified compared to Nicolle et al. (2011) may relate to different dependent measure used (momentary wellbeing vs. regret).
- **limitations_categorized:** limited ecological validity; confederate deception; post-hoc ROI selection; no traditional learning mechanism; limited generalizability
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `eligibility_flag` (MEDIUM): The "RL model" here is not a standard learning model -- it is a momentary happiness model with exponential decay weighting of recent events. There are no learning rates, no value updating. Whether this constitutes "learning over time" is debatable. - `winning_model` (MEDIUM): The paper does not declare a single winner. Responsibility model has best R²; Responsibility Redux has best BIC/AIC. Both are presented as findings. - `coordinates_peak` (MEDIUM): Only 3 peak coordinates explicitly reported with MNI values. Anterior insula coordinates not given as peaks (only described as a cluster). Other contrast results list region names without coordinates. - `model_params` (HIGH): All parameters described in text. Mean fitted values not reported numerically (shown in figures only as bar plots). - `formula` (MEDIUM): Equations present but rendered with (cid:) artifacts from PDF extraction, making exact symbols uncertain.
- **cannot_find:** - Exact mean fitted parameter values (shown in figures but not in text) - Peak MNI coordinates for anterior insula responsibility effect - Peak coordinates for partner > self decision contrasts - Supplement (none exists for this preprint) - Preregistration status
- **other_notes:** This paper builds directly on Rutledge et al. (2014, 2016) methodology and code. The "reinforcement learning model" terminology in the paper is somewhat misleading -- these are happiness models with RL-derived variables (RPEs, EVs), not models of choice learning. The key social parameter (self_pRPE weight) captures how much the partner's prediction errors from one's own decisions affect momentary well-being. No supplement was found for this bioRxiv preprint.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = parametric
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_E_self_in_social_context
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_E_self_in_social_context
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_social_bonus
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_secondary_topic = self_other_boundary
- tax_rr_topic_prosocial_altruism
- tax_rr_topic_self_other_boundary
- tax_topic_prosocial_altruism
- tax_topic_self_other_boundary
