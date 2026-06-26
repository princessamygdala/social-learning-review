# Yoon et al. (2018)

- **study_id:** `aa29ab1115d964d7c_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Yoon, L., Somerville, L. H., & Kim, H. (2018). Development of MPFC function mediates shifts in self-protective behavior provoked by social feedback. *Nature Communications*, *9*, 3086. https://doi.org/10.1038/s41467-018-05553-2
- **citation_short:** Yoon et al. (2018)
- **doi:** 10.1038/s41467-018-05553-2
- **publication_type:** peer-reviewed journal---
- **year:** 2018.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofPsychology,KoreaUniversity,145Anam-ro,Seongbuk-gu,Seoul136-701,RepublicofKorea; laboratory-basedstudies2,4,many evaluated the partner’s artwork (Fig; DepartmentofPsychologyandCenterfor; University,Cambridge,MA02138,USA; ethatthedevelopmentof; laboratory twice,; ether with; emails: hackjinkim@korea.ac.kr
- **code_url:** 

## Computational level
- **study_focus:** Self-protective behavior learning; developmental shift in social feedback integration for self-protection
- **study_focus_short:** Self-protective behavior learning
- **learning_mode_description:** - Learning mode: Learning from others' evaluative feedback about one's own creative work to update the value of self-protective behavior (derogating the evaluator)   - Learning from:     - Source type (social): other (75 partners/evaluators)     - Source content (social): outcome (positive/negative/neutral creativity evaluation feedback on participant's artwork)   - Learning about:     - Target type (social): self (own social standing / self-protective value)     - Target content (social): state (mental state; value of self-protection / self-worth)
- **task_description:** In a reciprocal artwork evaluation task, participants (ages 10-25) viewed feedback from 75 partners on their own artwork, then evaluated each partner's artwork. Feedback was pre-determined (25 positive, 25 negative, 25 neutral) and participants made binary creativity judgments.
- **task_paradigm:** Self-evaluation / self-esteem task
- **players:** Single agent (participant), multi-target (75 fictitious partners)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Creative artworks (photographs), partner names (gender-neutral), light bulb icons (lit = creative, unlit = not creative) for feedback
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Age-related decrease in current feedback (cFB) influence on partner evaluation (F(1,56) = 5.420; no ES reported beyond F) - Age-related increase in accumulated feedback (accFB) influence (F(1,56) = 8.434) - Age x feedback type interaction (ANCOVA F(1,56) = 19.234) - Age-related decrease in RL learning rate (Bootstrap regression B = -0.029, 95% CI [-0.05 to -0.006]) - Learning rate positively correlated with cFB influence (Spearman r_s(53) = 0.383) - Learning rate negatively correlated with accFB influence (Spearman r_s(53) = -0.44) - VMPFC mediation of age-related decrease in cFB influence (indirect effect B = -0.02, 95% CI [-0.0382 to -0.0036]) - VMPFC mediation of age-related increase in accFB influence (indirect effect B = 0.02, 95% CI [0.0064 to 0.0405]) - RMPFC mediation of age-related increase in accFB influence (indirect effect B = 0.02, 95% CI [0.0035 to 0.0442]) - R-VMPFC mediation of age-related decrease in learning rate (indirect effect B = -0.02, 95% CI [-0.03 to -0.006]) - PPC mediation of age-related decrease in learning rate (indirect effect B = -0.01, 95% CI [-0.0244 to -0.0031]) - Replication in independent adult sample: accFB influence (t(27) = 2.874); learning rate median = 0.1372
- **effect_size:** MEDIUM — no standardized effect sizes (d, eta-squared) for main behavioral effects; only regression B, F-statistics, and Spearman correlations reported
- **learning_from:** Other (partners); social-evaluative feedback (positive/negative/neutral) on one's own artwork
- **learning_about:** Self; value of self-protection (self-protective motivation to derogate partners)
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** Rescorla-Wagner (1 free parameter: alpha learning rate); VSP_t = VSP_{t-1} + alpha * [FB_t - VSP_{t-1}]
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** Only one computational model tested: - [{"name": "RL (Rescorla-Wagner) for VSP updating", "family": "Rescorla-Wagner", "n_params": 1, "metric": "maximum log-likelihood"}] Note: A logistic regression model (Eq. 1) was also used as a descriptive behavioral model but was not compared against the RL model — they served different analytic purposes.
- **model_mb_mf:** MF (model-free)
- **model_params:** MEDIUM — mean learning rate across developmental sample not reported; only adult replication median (0.1372) given
- **social_param:** alpha (learning rate) — determines depth of social feedback integration for self-protection; lower alpha = more weight on accumulated social feedback history, higher alpha = more weight on immediate social feedback.
- **social_param_name:** alpha
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Maximum log-likelihood (used for parameter estimation only; no model comparison between competing models)
- **how_model_fit:** Individual-level fit; grid search over alpha (0 to 1, step 0.0001) maximizing log-likelihood of logistic regression predicting partner-evaluation decisions.
- **data_type_fit_to:** Choice behavior (binary partner-evaluation decisions)---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors)
- **contrast:** - GLM1: cFB parametric modulation at feedback receipt event, correlated with individual cFB influence → VMPFC (SVC FWE p < 0.05) - GLM1: accFB parametric modulation at partner-evaluation event, correlated with individual accFB influence → VMPFC (SVC FWE p < 0.05) and RMPFC (SVC FWE and whole-brain FWE p < 0.05) - GLM2: PE parametric modulation at feedback receipt event, negatively correlated with learning rate → R-VMPFC (SVC FWE and whole-brain FWE p < 0.05) and PPC (whole-brain FWE p < 0.05)
- **key_regions:** Self-protection triggered by current feedback in VMPFC; accumulated feedback effect in both VMPFC and RMPFC; RL prediction error signals negatively associated with learning rate in RMPFC extending into VMPFC (R-VMPFC) and posterior parietal cortex (PPC).
- **key_regions_abbrev:** vmPFC, mPFC, ACC, parietal
- **coordinates_peak:** - VMPFC (cFB, feedback receipt): 10, 24, -18 - VMPFC (accFB, partner evaluation): -6, 36, -14 - RMPFC (accFB, partner evaluation, SVC): -4, 62, 16 - RMPFC (accFB, partner evaluation, whole-brain): -4, 62, 16 - R-VMPFC (PE, SVC): -6, 62, 10 - VMPFC (PE, SVC): 10, 50, -18 - R-VMPFC (PE, whole-brain): -6, 62, 10 - PPC (PE, whole-brain): 6, -54, 26 (HIGH — all reported in main text)
- **analysis_type:** Both (ROI with SVC FWE correction as primary; exploratory whole-brain FWE as secondary)---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 60 total recruited; N = 58 behavioral (2 excluded for uniform button press); N = 57 fMRI (1 additional excluded for head motion); ages 10-25 (mean = 16.4; 29 males, 29 females). Independent replication: N = 28 adults (mean age = 23.1, range 20-27). 3 additional participants excluded from RL analysis for violating model assumption.
- **population_category:** healthy adults
- **population_age_range:** 10–25
- **ecological_validity:** Novel reciprocal artwork evaluation task uses creative works made by participants, increasing personal investment. However, feedback was pre-determined and fictitious (participants were deceived about having real partners), and binary creativity judgments are limited in ecological validity compared to real social interactions. Cross-sectional design limits developmental inferences.
- **eligibility_flag:** 
- **concerns:** - Only one RL model tested; no model comparison with alternative models (e.g., different learning rules, dual learning rates) - Grid search with step size 0.0001 for parameter estimation rather than more principled optimization - Cross-sectional design used to make developmental claims - No parameter recovery or model recovery analyses - Three participants excluded from RL analysis for violating model assumption (positive evaluation when VSP high) — potential selection bias - Effect sizes for main behavioral findings reported only as F-statistics and regression coefficients; no standardized effect sizes (Cohen's d, eta-squared) - Deceptive cover story (fictitious partners)
- **limitations_reported:** A future study including nonsocial-evaluative feedback (e.g., from a computer rather than a human) would further elucidate whether the RMPFC is uniquely involved in self-protective behavior due to social feedback; given the cross-sectional nature of the present study, a future longitudinal study accompanied by additional collection of hormonal levels, structural brain maturation, and environmental factors would be needed to have a more complete view of intra-individual developmental changes in self-protective behavior.
- **limitations_categorized:** Limited ecological validity (no non-social control condition); cross-sectional design (no longitudinal data); limited generalizability (no hormonal/structural/environmental measures)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 4.0
- **wc_total:** 4.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** yes
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_children
- pop_healthy_adults
- rr_pop_adolescents
- rr_pop_children
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = shared
- spec_source = social
- spec_target = partly
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = social_approval_reward
- tax_rr_secondary_topic = self_esteem
- tax_rr_topic_self_esteem
- tax_rr_topic_social_approval_reward
- tax_topic_self_esteem
- tax_topic_social_approval_reward
