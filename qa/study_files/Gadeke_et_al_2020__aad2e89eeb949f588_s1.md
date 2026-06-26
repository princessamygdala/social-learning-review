# Gadeke et al. (2020)

- **study_id:** `aad2e89eeb949f588_s1`
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
- **study_focus:** Social responsibility learning -- how responsibility for risky choices affecting an interaction partner modulates momentary subjective well-being (happiness) through reward prediction errors.
- **study_focus_short:** Social responsibility learning -- how responsibility for risky choices
- **learning_mode_description:** - Learning mode: Learning how one's own vs. another's choices leading to outcomes for self and partner affect momentary well-being   - Learning from:     - Source type (social): other (partner) and self -- **joint** (outcomes result from either self or partner choosing)     - Source content (non-social): outcome (monetary reward prediction errors for self and partner)   - Learning about:     - Target type (social): self and other (partner) -- **joint**     - Target content (social): state (momentary subjective well-being / emotional state modulated by social responsibility)
- **task_description:** Participants chose between a safe and risky monetary option in three conditions: choosing for self only, choosing for self and partner, or the partner choosing for both. After risky choices, gambles were played out independently for both players, and participants rated momentary happiness every two trials.
- **task_paradigm:** Risky decision-making
- **players:** Single agent (participant), dyadic (confederate partner; partner choices simulated)
- **n_players:** dyadic (2)
- **partner_type:** confederate
- **stimuli:** Monetary gamble options (safe vs. risky), happiness rating scale
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Happiness was lower after negative partner outcomes from own vs. partner's choices (responsibility effect; d = 0.56, BF10 = 32 for self-win/partner-lost; d = 0.54, BF10 = 19 for self-lost/partner-lost) - Only advantageous inequality aversion found (d > 0.6, BF10 > 186 when participant won unequal) - Responsibility model had highest R² (Mean R² = 0.370) vs. Basic (0.328), Partner RPE (0.362), Guilt-envy (0.354) - Responsibility Redux had best BIC/AIC (tied with Basic and Partner RPE for BIC) - self_pRPE weight significantly > 0 (Z = 3.52, p = 0.0004); partner_pRPE weight not significant (Z = 1.44, p = 0.15)
- **effect_size:** See above -- Cohen's d, BF10, R², eta-squared reported inline.
- **learning_from:** Self and other (partner); monetary outcomes / reward prediction errors from risky choices
- **learning_about:** Self and other (partner); emotional impact (momentary happiness) modulated by responsibility  ---  #### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Responsibility Redux: Happiness(t) = sum[gamma^(t-j) * (w1*CR_j + w2*EV_j + w3*sRPE_j + w4*self_pRPE_j)] (4 params + gamma). Note: Responsibility model (5 params) had highest R² but Responsibility Redux (4 params) had best BIC/AIC. The paper treats both as "best" depending on criterion.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "Basic", "family": "RL/RW happiness", "n_params": 3, "metric": "R², adj R², BIC, AIC"} - {"name": "Inequality", "family": "RL/RW happiness", "n_params": 4, "metric": "R², adj R², BIC, AIC"} - {"name": "Guilt-envy", "family": "RL/RW happiness", "n_params": 5, "metric": "R², adj R², BIC, AIC"} - {"name": "Partner RPE", "family": "RL/RW happiness", "n_params": 4, "metric": "R², adj R², BIC, AIC"} - {"name": "Responsibility", "family": "RL/RW happiness", "n_params": 5, "metric": "R², adj R², BIC, AIC"} - {"name": "Responsibility Redux", "family": "RL/RW happiness", "n_params": 4, "metric": "R², adj R², BIC, AIC"}
- **model_mb_mf:** MF (model-free prediction error based)
- **model_params:** - w1 (CR weight): weight on certain rewards - w2 (EV weight): weight on expected value of chosen gambles - w3 (sRPE weight): weight on self reward prediction error - w4 (self_pRPE weight) [S]: weight on partner's RPE resulting from participant's choices - gamma (forgetting factor): exponential decay over trials (median 0.39-0.44) - (Responsibility model adds w5 = partner_pRPE weight [S])
- **social_param:** w4 (self_pRPE) [S]: weight capturing the influence of partner's reward prediction errors resulting from participant's own choices on momentary happiness -- the social responsibility parameter. Also w5 (partner_pRPE) [S] in the full Responsibility model.
- **social_param_name:** w4
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** R², adjusted R², BIC (summed across subjects), AIC (summed across subjects), with repeated-measures ANOVA and Bonferroni-corrected post-hoc t-tests.
- **how_model_fit:** individual-level-fit (Levenberg-Marquardt algorithm for non-linear least squares, fitted per participant)
- **data_type_fit_to:** self-report ratings (momentary happiness)  ---  #### IMPLEMENTATION LEVEL (Study 1)

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  #### PAPER QUALITY (Study 1)
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 40 (14 male, mean age 26.1, range 22-31)
- **population_category:** healthy adults
- **population_age_range:** 22–31
- **ecological_validity:** Moderate. Uses a confederate partner with ice-breaker to create non-competitive atmosphere, but partner choices are simulated, and the gamble paradigm is abstract. Monetary stakes are small (0-10 EUR).
- **eligibility_flag:** 
- **concerns:** Partner choices were simulated by an algorithm (always chose highest EV), not by a real human -- participants were deceived about this. The "social" nature of the partner interaction is therefore limited. Models are fit to happiness ratings, not choice behavior. The model is not a learning model in the traditional sense (no trial-by-trial parameter updating / no learning rate) -- it is a weighted regression of momentary happiness on recent reward history. This raises an eligibility question about whether "learning over time" truly occurs, though the exponential decay/forgetting factor does capture temporal dynamics.
- **limitations_reported:** Authors did not ask participants to specifically report which emotions they experienced; cannot ascertain whether participants felt guilt, regret, or disappointment specifically; decisions never only affected the partner, which may have diluted differences in risk attitude; non-competitive context may explain absence of disadvantageous inequality aversion; have not tested paradigm in competitive context.
- **limitations_categorized:** limited ecological validity; task simplicity; no direct emotion measurement; limited generalizability (non-competitive context only)
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
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_E_self_in_social_context
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_social_weight
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
