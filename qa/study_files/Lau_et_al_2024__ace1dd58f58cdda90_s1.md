# Lau et al. (2024)

- **study_id:** `ace1dd58f58cdda90_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Lau, I. H. W., Norman, J., Stothard, M., Carlisi, C. O., & Moutoussis, M. (2024). Jumping to attributions during social evaluation. *Scientific Reports*, *14*, 15447. https://doi.org/10.1038/s41598-024-65704-y
- **citation_short:** Lau et al. (2024)
- **doi:** 10.1038/s41598-024-65704-y
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** Department of Imaging Neuroscience, University College London, London,; Division of Psychology and Language Science, University; University of Cambridge, Cambridge, UK; University College London, London, UK; ether the rater liked or disliked; ether the current rater will; College London, London, UK; Institute of Cognitive; emails: c.carlisi@ucl.ac.uk
- **code_url:** 

## Computational level
- **study_focus:** social evaluation learning; trait inference; attribution learning
- **study_focus_short:** social evaluation learning; trait inference; attribution learning
- **learning_mode_description:** - Learning mode: Learning from raters' evaluative feedback (positive/negative personality words) about the attributes and dispositions of raters toward self and other.     - Learning from:       - Source type (social): other (computerized rater persona)       - Source content (social): feedback (positive/negative word selections by rater)     - Learning about:       - Target type (social): other (rater's disposition toward self or another ratee)         - If joint: not joint       - Target content (social): state (mental state; rater's evaluative disposition — positive vs. negative attribution)
- **task_description:** Participants predicted whether computerized raters would select a positive or negative personality word to describe them (self-referential) or another persona (other-referential) across 8 blocks of 20 trials, with feedback provided after each prediction. Blocks varied in feedback positivity (80%, 50%, or 20% positive) and included repeat-rater conditions.
- **task_paradigm:** Self-evaluation / self-esteem task
- **players:** Single agent (participant), multi-target (8 computerized raters across blocks; 1 other-referential ratee)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Positive/negative personality word pairs (e.g., caring/indifferent), customizable avatars, school-context cover story
- **method:** online / behavioural
- **method_full:** behavioural (online)
- **main_result:** - Classify-refine model outperformed beta-belief model (total BIC: 62,472 vs. 63,746; Wilcoxon p = 2.27e-5)   - Anxiety factor scores predicted by winning model parameters (adjusted R² = 0.064, p = 0.047)   - Policy certainty (aEv) associated with higher anxiety (β = 0.23, p = 0.028)   - Decision noise (αPrec) associated with higher anxiety (β = -0.29, p = 0.018)   - Decision noise predicted mood disorder diagnosis over and above anxiety symptoms (McFadden's R² = 0.11, β = -0.83, p = 0.011)   - Decision noise survived correction for anxiety factor scores (β = -0.63, p = 0.041)
- **effect_size:** adjusted R² = 0.064 (regression of model params on anxiety); McFadden's R² = 0.11 (logistic regression on mood disorder diagnosis); β = 0.23 (aEv on anxiety); β = -0.29 (αPrec on anxiety); β = -0.83 (αPrec on mood diagnosis); β = -0.63 (αPrec corrected for anxiety)
- **learning_from:** Other (computerized rater); evaluative feedback (positive/negative word selections)
- **learning_about:** Other (rater's evaluative disposition toward self or other ratee); state (positive vs. negative attribution)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** Classify-refine (Hidden Markov/Active Inference core; 9 free params: pS+, pO+, dEv, aEv, αPrec, lps, λgen, λrep, mem; 2 fixed: wAttr, w0) with softmax + uniform lapse response function
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** - [{"name": "Classify-refine (winning; model 8b in Fig. 4)", "family": "Hidden Markov / Active Inference", "n_params": 11 (9 free + 2 fixed), "metric": "BIC"},   - {"name": "Beta-belief (best in class)", "family": "Bayesian beta-distribution", "n_params": "comparable", "metric": "BIC"},   - {"name": "Multiple classify-refine variants (Fig. 4: models 1-10+)", "family": "Hidden Markov / Active Inference", "n_params": "varies", "metric": "BIC"},   - {"name": "Multiple beta-belief variants", "family": "Bayesian beta-distribution", "n_params": "varies", "metric": "BIC"}]   - Note: Fig. 4 shows approximately 10+ model variants in each class tested in a hierarchical comparison; exact count of all variants not enumerated individually in text.
- **model_mb_mf:** Bayesian
- **model_params:** - pS+ [S]: initial belief of positive attribution of self (positivity prior for self)   - pO+ [S]: initial belief of positive attribution of other (positivity prior for other)   - dEv [S]: attribution certainty — strength of prior belief about rater's disposition (classify stage)   - aEv [S]: policy certainty — initial certainty about rater's response policy (refine stage)   - αPrec: decision precision (inverse temperature)   - lps: noise floor / lapse parameter (uniform lapse rate)   - λgen: learning rate across different raters (between-block)   - λrep: learning rate within repeated raters (between repeated blocks)   - mem: memory/decay parameter (forgetting of evidence trial to trial)   - wAttr (fixed): weight of attribution in rater's positivity policy function   - w0 (fixed): bias (intercept) in rater's positivity policy function   - Note: Mean fitted values not individually reported in text; wAttr and w0 fixed to population median.
- **social_param:** pS+ [S]: initial positive attribution belief for self; pO+ [S]: initial positive attribution belief for other; dEv [S]: attribution certainty (strength of classification prior); aEv [S]: policy certainty (rigidity of rater policy beliefs)
- **social_param_name:** pS+
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (summed across participants; individual-level comparison via paired Wilcoxon test)
- **how_model_fit:** individual-level-fit (MAP with weakly informative priors; adaptive grid search optimization)
- **data_type_fit_to:** choice behavior (continuous VAS positivity ratings, 0-100)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 130 (from initial 154; 24 excluded for attention checks [6] and technical issues [18]); mean age = 37.5, SD = 10.5; predominantly White British; 33.8% self-reported current/historic depression or anxiety diagnosis
- **population_category:** clinical
- **population_age_range:** M=37.5
- **ecological_validity:** Moderate; online task with customizable avatars and school cover story improves engagement; stakeholder (adolescent) input on task design; computerized raters limit ecological validity; task adapted for future adolescent use but tested in adults
- **eligibility_flag:** 
- **concerns:** Task was designed for adolescents but tested in adults only — generalizability to intended population not established; some neutral blocks duplicated due to JavaScript randomization bug (acknowledged in supplement technical notes); lapse parameter (lps) showed poor recovery (r = 0.02); Anxiety factor analysis yielded only one usable factor (Depression factor excluded due to poor stability); exploratory regression with 11 predictors on N=130 risks overfitting; no model recovery (confusion matrix) reported
- **limitations_reported:** Sample size was relatively small (n = 130) and contained modest variation in symptomatology, resulting in limited reproducibility and generalizability of findings; limited scope of clinical measurements used, resulting in robust factor scores only about anxiety; incorporation of attentional checks might be systematically confounded by careless and/or insufficient effort that might be clinically meaningful; exploratory study revealed an unexpected main effect of ethnicity
- **limitations_categorized:** sample size; limited generalizability; limited clinical measurement scope; potential confound from attention checks; unexpected ethnicity effects
- **preregistered:** Yes
- **wc_rule1:** Yes (task designed to probe social evaluation learning with classify-refine mechanism)
- **wc_rule2:** Yes (multiple model classes compared: classify-refine vs. beta-belief, with variants)
- **wc_rule3:** Partial (synthetic data generated for correlation with experimental data [Fig. S4], but no pre-fitting simulation described)
- **wc_rule4:** Yes (MAP fitting with weakly informative priors)
- **wc_rule5:** Yes (parameter recovery performed; reported in Supplement Figs. S7A-S7I; r = 0.72-0.97 for most params; lps not recovered)
- **wc_rule6:** No (no model recovery / confusion matrix reported)
- **wc_rule7:** Yes (BIC comparison across model classes and variants)
- **wc_rule8:** Partial (synthetic-experimental data correlations shown [Fig. S4] but no formal posterior predictive check)
- **wc_rule9:** Yes (parameter correlations with anxiety factor scores and mood diagnosis explored)
- **wc_rule10:** Partial (data/code stated to be on OSF upon acceptance; preregistered at https://osf.io/s25dn)
- **wc_score:** 0
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params (MEDIUM): individual mean fitted parameter values not reported in text or supplement   - all_models_tested (MEDIUM): exact number and specifications of all model variants in Fig. 4 hierarchy not individually enumerated   - wc_rule3 (MEDIUM): synthetic data generated post-fitting for validation but unclear if pre-fitting simulations were done   - wc_rule8 (MEDIUM): correlation of synthetic and experimental data is partial posterior predictive check
- **cannot_find:** Individual mean fitted parameter values for the 9 free parameters; exact count and specifications of all model variants tested in the hierarchical comparison (Fig. 4 shows ~10+ per class but details not all enumerated)
- **other_notes:** This paper is closely related to Hopkins et al. (2021) and Barnby et al. (2020, 2022) which use similar active inference frameworks. The SELT-R task is an evolution of the original SELT (Button et al., 2015). JavaScript randomization bug affected some neutral blocks (noted in supplement). Preregistered at OSF (https://osf.io/s25dn). The "classify-refine" framework is a novel contribution modeling rapid initial attribution followed by gradual policy learning — distinct from standard Rescorla-Wagner or simple Bayesian beta-belief models.
- **re_extract_flag:** FALSE

## Taxonomy / categorization (active codes only)
- pop_anxiety
- pop_depression
- pop_healthy_adults
- rr_pop_anxiety
- rr_pop_depression
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_context = partly
- spec_depth = parametric
- spec_locus = target
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_bayesian
- tax_param_decay
- tax_param_precision
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_learning_rate
- tax_rr_param_precision
- tax_rr_primary_topic = trait_impression
- tax_rr_secondary_topic = self_esteem
- tax_rr_topic_self_esteem
- tax_rr_topic_trait_impression
- tax_topic_self_esteem
- tax_topic_trait_impression
