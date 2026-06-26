# Tehrani-Safa et al. (2023)

- **study_id:** `a70bb29710dadbc8a_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Tehrani-Safa, A. H., Ghaderi, R., & Sarabi-Jamab, A. (2023). Bayesian observational learning of other's risk attitude: Investigating the role of inferential uncertainty in the approximate delta rule social inferences. *Manuscript* (August 24, 2023).
- **citation_short:** Tehrani-Safa et al. (2023)
- **doi:** Not reported in the text. No DOI found.
- **publication_type:** appears to be a preprint/manuscript (dated august 24, 2023; formatted like a plos-style submission but no journal header or volume/issue info). confidence: medium.
- **year:** 2023.0
- **field_of_study:** Behavioural economics / Economics
- **affiliations_raw:** mitation learning, however, involves calculating the difference between what another; Institute for Cognitive and Brain Sciences, Shahid Beheshti University, Tehran, P; mitation learning, which does not involve learning about internal variables,; School of Cognitive Sciences, Institute for Research in Fundamental Sciences; mitation, and (3) inference about other people’s beliefs and intentions; emails: atiye.sarabi@gmail.com
- **code_url:** 

## Computational level
- **study_focus:** Observational learning of another person's risk attitude (trait inference from observed risky choices).
- **study_focus_short:** Observational learning of another person's risk attitude
- **learning_mode_description:** - Learning mode: Learning another person's risk attitude by observing their choices between risky gambles and sure options.   - Learning from:     - Source type (social): other (observed decision-maker/agent)     - Source content (social): action/policy (accept/reject gamble choices)   - Learning about:     - Target type (social): other (observed decision-maker/agent)     - Target content (social): state (mental state; risk attitude trait, rho)
- **task_description:** An observer watches another person's sequential choices between a risky gamble (with probability p and reward r) and a guaranteed payment of $10. The observer must infer the other person's risk attitude (rho) from these observed accept/reject choices across 56 trials (2 blocks of 28).
- **task_paradigm:** Observational learning task
- **players:** Single agent (observer/participant), single target (observed decision-maker). The paper uses data from Suzuki et al. (2016) where participants observed another agent's choices.
- **n_players:** single agent (1)
- **partner_type:** unclear
- **stimuli:** Risky gambles displayed as pie charts showing reward probability and magnitude vs. a guaranteed $10 payment; binary accept/reject choices of the observed agent.
- **method:** behavioural
- **method_full:** Behavioural (computational modeling on behavioral data from Suzuki et al., 2016; no neuroimaging in this paper).
- **main_result:** - Bayesian Learner (BL) outperformed Rescorla-Wagner (R-W) model across all three sessions via BIC and LME   - Session 1: BL BIC = 571.89, R-W BIC = 631.98; BL LME = -277.79, R-W LME = -313.44   - Session 3: BL BIC = 427.35, R-W BIC = 521.36; BL LME = -200.82, R-W LME = -259.29   - Session 5: BL BIC = 445.05, R-W BIC = 496.19; BL LME = -210.40, R-W LME = -234.89 - RFX Bayesian Model Selection: Exceedance Frequency = 0.99, Exceedance Probability = 1, Protected Exceedance Probability = 1 in favor of BL - BL's dynamic learning rate decreases over trials, reflecting exploration-to-exploitation transition - Accumulated predictive uncertainty (sigma_C) determines inferential uncertainty (sigma_rho), which drives the learning rate
- **effect_size:** EF = 0.99, EP = 1.0, PEP = 1.0 (Bayesian model selection). BIC differences across sessions: 60.09, 93.01, 51.14 in favor of BL. No Cohen's d, r, or beta reported.
- **learning_from:** Other (observed agent); action/policy (risky gamble choices).
- **learning_about:** Other (observed agent); state (risk attitude trait, rho).  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Bayesian Learner (approximate variational Bayesian observer with delta-rule update; 1 free parameter: beta). Update rule: mu_rho(k) = mu_rho(k-1) + alpha(k) * delta(k), where alpha(k) = beta * gamma(k) * sigma_rho(k) is a dynamic learning rate, delta(k) = C_o(k) - S(F(mu_rho(k-1))) is prediction error, and sigma_rho(k) is updated via accumulated predictive uncertainty.
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** - {"name": "Bayesian Learner (BL)", "family": "Bayesian belief updating (variational)", "n_params": 1, "metric": "BIC, LME, RFX-BMS"} - {"name": "Rescorla-Wagner Learner (R-W)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BIC, LME, RFX-BMS"}
- **model_mb_mf:** MB (model-based; the Bayesian learner inverts a generative model of the other's decision-making process)
- **model_params:** - beta: inverse temperature / choice stochasticity parameter of the observed agent (fitted per participant). BL has 1 free parameter (beta only; learning rate alpha is derived from Bayesian updating). Example fitted values for one participant: Session 1: beta_BL = 1.45; Session 3: beta_BL = 0.54; Session 5: beta_BL = 0.77. - R-W model: alpha (fixed learning rate) + beta (inverse temperature) = 2 free parameters. Example: Session 1: alpha_RW = 0.08, beta_RW = 1.44. - Prior parameters: mu_rho(0) = 1, sigma_rho(0) = 0.01 (set, not fitted).
- **social_param:** rho (risk attitude of the other agent) [S] -- the latent social parameter being inferred; the entire model is designed to estimate another person's hidden risk attitude from their observed choices.
- **social_param_name:** rho
- **social_param_value:** 1
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC, Log Model Evidence (LME / Free Energy approximation), Random-Effects Bayesian Model Selection (RFX-BMS) with Exceedance Probability and Protected Exceedance Probability.
- **how_model_fit:** Individual-level fit (BFGS optimization via TAPAS toolbox maximizing log-joint posterior density).
- **data_type_fit_to:** Choice behavior (binary accept/reject decisions of observed agent).  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A (no neuroimaging)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Data from Suzuki et al. (2016); the paper does not report the exact N of participants re-analyzed. The original Suzuki et al. (2016) study had N=24 (behavioral + fMRI). The current paper states it used data from sessions 1, 3, and 5 of that study. Exact N used here: not explicitly stated. Confidence: LOW.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low ecological validity. Task uses abstract gambles with pie-chart stimuli; the observed "agent" follows a computational model of risky choice. No real social interaction -- observer watches pre-generated choices. Gamble parameters are artificial (fixed guaranteed payment of $10, limited probability range 0.3-0.5).
- **eligibility_flag:** 
- **concerns:** - The paper re-uses data from Suzuki et al. (2016) but does not clearly state the sample size used in model fitting. - Only two models compared (BL vs. R-W), limiting the model space explored. - The observed "agent" in the task follows a computational generative model, not a real human, which limits the social realism. - No parameter recovery analysis reported. - No model recovery analysis reported. - No posterior predictive checks reported. - Paper appears to be a manuscript/preprint (dated August 2023) -- publication status unclear. - The paper is primarily a theoretical/methodological contribution demonstrating the Bayesian observer model, with limited empirical validation.
- **limitations_reported:** The paper does not include a dedicated limitations section. The discussion notes that the Rescorla-Wagner model "does not accurately replicate the human exploration-exploitation heuristic" and that "a fixed learning rate model is not a precise representation of behavior for this task," but these are limitations of the competing model, not of their own approach. No explicit self-identified limitations.
- **limitations_categorized:** No limitations section; limited model comparison space; no parameter recovery; no model recovery; reliance on secondary data.
- **preregistered:** No
- **wc_rule1:** Partial
- **wc_rule2:** Partial
- **wc_rule3:** Yes
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
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - sample_size: LOW -- exact N of participants re-analyzed not stated in this paper - publication_type: MEDIUM -- appears to be preprint/manuscript, no journal or DOI identified - doi: LOW -- not found in paper text
- **cannot_find:** - DOI - Exact sample size used in model fitting - Authors' own limitations - Data/code availability statement
- **other_notes:** - This paper uses data from Suzuki, Jensen, Bossaerts, & O'Doherty (2016, PNAS). Potential overlap with that paper if also included in the review -- flag for duplicate dataset check. - The paper is primarily a theoretical contribution deriving the approximate Bayesian delta-rule for social inference of risk attitude, with empirical validation as secondary. - The supplement/appendix material (S1, S2) is embedded within the main manuscript text (not a separate file), containing mathematical derivations. - No neuroimaging conducted in this paper (though the original Suzuki et al. 2016 dataset includes fMRI data, it is not analyzed here).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_mentalizing_inference
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_G_uncertainty_volatility
- tax_mod_action_observation
- tax_mod_mentalizing_inference
- tax_model_MB
- tax_model_bayesian
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_learning_rate
- tax_rr_param_precision
- tax_rr_primary_topic = trait_impression
- tax_rr_secondary_topic = social_uncertainty
- tax_rr_topic_social_uncertainty
- tax_rr_topic_trait_impression
- tax_topic_social_uncertainty
- tax_topic_trait_impression
