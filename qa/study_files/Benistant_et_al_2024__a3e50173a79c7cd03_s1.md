# Benistant et al. (2024)

- **study_id:** `a3e50173a79c7cd03_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Benistant, J., Guigon, V., Nicolas, A., Derrington, E., & Dreher, J.-C. (2024). Dynamic valuation bias explains social influence on cheating behavior. *bioRxiv*. https://doi.org/10.1101/2024.05.21.594859
- **citation_short:** Benistant et al. (2024)
- **doi:** 10.1101/2024.05.21.594859
- **publication_type:** preprint
- **year:** 2024.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** mitation of these two previous accounts of social influence is that they did not consider; ether social influence shapes our individual beliefs, as behavior reflecting social; mited to dishonesty, but can be observed in domains such as risk-related decision; CNRS, Institut des Sciences Cognitives Marc Jeannerod, Bron, France; CNRS, IESEG School of Management, UMR 9221 - LEM - Lille Économie; ether, these findings provide a mechanistic understanding of how; mitigate uncertainty about others’ true levels of; Université Lyon 1 Claude Bernard, France; emails: julien.benistant@univ-lille.fr, dreher
- **code_url:** 

## Computational level
- **study_focus:** Social influence on cheating behavior / moral contagion -- how learning about others' dishonesty dynamically biases one's own valuation of cheating.
- **study_focus_short:** Social influence on cheating behavior / moral contagion -- how learning about
- **learning_mode_description:** - Learning mode: Learning from others' observed cheating behavior about the social norm of (dis)honesty, which dynamically biases one's own valuation of cheating.   - Learning from:     - Source type (social): other (group of 10 simulated individuals)     - Source content (social): action/policy (others' cheating choices and feedback on those choices)   - Learning about:     - Target type (social): other (group members' preferences)     - Target content (social): state (mental state; moral preferences / dishonesty tendency)   - Secondary learning-about (implicit):     - Target type (non-social): self (own valuation of cheating is biased)     - Target content (non-social): outcome (valuation bias on cheating decision value)
- **task_description:** Participants played a cheating game with Solo trials (choose to report an honest or dishonest die outcome for varying payoffs) and Predict trials (predict whether a simulated group member cheated), across three blocks: a baseline block (Solo only) and two blocks interleaving Solo and Predict trials with either a dishonest (88% cheating) or honest (22% cheating) simulated group.
- **task_paradigm:** Cheating / dishonesty task
- **players:** Single agent (participant), multi-target (simulated group of 10 others; 2 groups: dishonest and honest)
- **n_players:** small group (3-4)
- **partner_type:** unclear
- **stimuli:** Die roll outcomes, monetary payoffs (EUR 0-10), binary choice (honest vs. dishonest report), prediction feedback
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Cheating increased significantly in Dishonest Group vs. Baseline (margins contrast = 0.148 +/- 0.037, p < 0.001) - Cheating increased in Dishonest Group vs. Honest Group (margins contrast = 0.101 +/- 0.027, p = 0.001) - No significant difference Honest Group vs. Baseline (margins = 0.047 +/- 0.025, p = 0.170) - VB-Dynamic model won model selection (pEP = 0.672) - Conformity parameter gamma significantly higher in Dishonest vs. Honest Group (rank sum test, p < 0.001) - Own preference parameter alpha: mean = 0.192 +/- 0.022 (p < 0.001); delta: mean = -0.684 +/- 0.178 (p = 0.001) - lPFC: dynamic valuation bias x conformity gamma, T = 5.32 (peak: -39, 27, 9) - pSTS-TPJ: prediction of others' cheating, T = 4.39 (peak: 54, 0, -9) and T = 6.81 (peak: -36, -24, 48 - left motor cortex cluster) - dACC: negative correlation with relative choice value, T = 4.12 (peak: 18, 27, 48) - Ventral striatum: prediction error, T = 5.93 (peak: -12, 3, -12)
- **effect_size:** MEDIUM confidence -- only marginal effects and T-values reported; no standardized behavioral effect sizes
- **learning_from:** Other (group); feedback on others' cheating choices in Predict trials
- **learning_about:** Others' dishonesty preferences (moral preferences of group members); dynamic bias on own cheating valuation
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** VB-Dynamic: DeltaDV(cheat) = alpha(pi_Cheat - pi_Honest) + delta + gamma * P(Cheat)_t^O, where P(Cheat)_t^O is inferred from BPL-Self model. Parameters: alpha (money sensitivity), delta (fixed moral cost), gamma (conformity, per group condition [S]), plus BPL learning parameters (mu_alpha^o, mu_delta^o, sigma^o, beta).
- **model_family:** Bayesian
- **model_class:** PE learning
- **all_models_tested:** 1. **PS-Fixed** (Fixed Preference Shift): preferences alpha, delta differ per condition. Family: utility function. n_params: 6 (alpha_B, alpha_D, alpha_H, delta_B, delta_D, delta_H) + learning params. Metric: pEP (BMS). 2. **VB-Fixed** (Fixed Valuation Bias): fixed bias theta per group condition added to DV. Family: utility function. n_params: 2 (alpha, delta) + 2 (theta_D, theta_H) + learning params. Metric: pEP. 3. **PS-Dynamic** (Dynamic Preference Shift): weighted average of own and learned others' preferences via omega_A, omega_D per condition. Family: Bayesian + utility. n_params: alpha, delta + 4 omega params + learning params. Metric: pEP. 4. **VB-Dynamic** (Dynamic Valuation Bias; WINNER): alpha, delta + gamma per condition * learned P(Cheat). Family: Bayesian + utility. n_params: alpha, delta + 2 gamma + learning params. Metric: pEP.  Additionally, in preliminary steps: - 2 utility functions tested (Fixed cost vs. Variable cost, plus mixed variants) -- Fixed cost won (pEP = 0.999) - 6 BPL learning models tested (3 prior types x 2 utility functions) -- BPL-Self with Fixed cost won (pEP = 0.907)
- **model_mb_mf:** Bayesian (model-based social learning component feeding into a value-based decision model)
- **model_params:** MEDIUM confidence -- exact number of free parameters in the full VB-Dynamic model is not explicitly totaled; inferred from equations
- **social_param:** gamma -- degree of conformity to others' cheating behavior; modulates dynamic valuation bias by scaling the inferred probability that others would cheat [S]
- **social_param_name:** gamma
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Protected Exceedance Probability (pEP) from random-effects Bayesian Model Selection (BMS), using free energy as lower bound of model evidence (VBA toolbox)
- **how_model_fit:** Individual-level fit (parameters estimated per participant)
- **data_type_fit_to:** Choice behavior (cheating decisions in Solo trials + predictions in Predict trials)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors from computational model)
- **contrast:** - GLM1: Dynamic valuation bias (learned P(others cheat)) at Solo trial choice stage, modulated by gamma at 2nd level -- lPFC negatively correlated with gamma in Dishonest condition (T = 5.32) - GLM2: Learned probability others cheated at Predict prediction stage -- bilateral pSTS-TPJ positively (T = 4.39) - GLM2: Relative chosen value DV(Chosen) - DV(Unchosen) in Solo trials -- dACC negatively (T = 4.12) - GLM2: Prediction error at Predict feedback stage -- bilateral ventral striatum positively (T = 5.93)
- **key_regions:** Social norm internalization (dynamic valuation bias) in left lPFC modulated by conformity; simulation of others' cheating in bilateral pSTS-TPJ; choice conflict in dACC; social prediction error in ventral striatum.
- **key_regions_abbrev:** VS, striatum, dACC, ACC, TPJ, STS
- **coordinates_peak:** - Left lPFC: -39, 27, 9 (dynamic valuation bias x gamma, T = 5.32, k = 152) - Right STS: 54, 0, -9 (others' cheat probability, T = 4.39, k = 1138) - Left motor cortex: -36, -24, 48 (others' cheat probability, T = 6.81, k = 3618) - Cerebellum: 30, -45, -33 (T = 4.76, k = 197); 15, -66, -57 (T = 4.54, k = 509) - Cuneus: 12, -78, 24 (T = 4.97, k = 184) - dACC: 18, 27, 48 (relative choice value, T = 4.12, k = 212) - Ventral striatum: -12, 3, -12 (prediction error, T = 5.93, k = 177) - Left motor cortex: -30, -18, 51 (prediction error, T = 3.68, k = 207) - dACC: 0, 33, 39 (prediction error negative, T = 4.41, k = 289) - Right angular: 30, -54, 42 (prediction error negative, T = 4.37, k = 210)
- **analysis_type:** Whole-brain (p < 0.05 FWE cluster-corrected, initial threshold p < 0.001 uncorrected)  ---  ### QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 32 recruited; N = 31 analyzed (1 excluded for always cheating + disbelief); N = 28 for model-based analyses and fMRI (3 additional excluded for always cheating or always honest in Baseline). Mean age = 22.87 years (SD = 0.58), 14 males.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Lab-based fMRI cheating game with simulated (not real) group members. Payoffs were real (incentive-compatible). Anonymity was reinforced. Deception about group members being real limits ecological validity, though debriefing confirmed most participants believed the scenario. The sequential learning design adds some naturalistic dynamics compared to one-shot social influence paradigms.
- **eligibility_flag:** 
- **concerns:** - Preprint (not peer-reviewed) - Simulated rather than real social partners -- limits generalizability of social influence findings - Small sample (N = 28 for main analyses) - VB-Dynamic model won with pEP = 0.672, which is moderate (not strongly dominant) - No parameter recovery or model recovery reported - The "left motor cortex" cluster (peak -36, -24, 48) reported under "others' cheat probability" is anatomically unusual for this signal and may reflect motor confounds - No effect sizes beyond marginal effects and T-values; no standardized effect sizes (d, r, eta-squared)
- **limitations_reported:** Participants learned quickly (accurate after ~10 trials), limiting the dynamic range of the learning manipulation; "fixed" models were not tested with more volatile or uncertain social environments which would induce slower learning; the asymmetry of social influence (dishonest > honest contagion) could not be explained by different levels of social proximity as group members were anonymous.
- **limitations_categorized:** Task simplicity; limited ecological validity; sample size; no parameter recovery; moderate model evidence  ---  ### WC CHECKLIST  1. **Design a good experiment:** Yes -- task engages social learning and social influence on cheating with controlled manipulation 2. **Design good models:** Yes -- 4 social influence models representing distinct hypotheses (fixed/dynamic x preference shift/valuation bias), plus utility function and learning model comparisons 3. **Simulate, simulate, simulate:** Partial -- group members' behavior was simulated from pilot data, but no explicit simulation of candidate models before fitting to assess identifiability 4. **Fit the parameters:** Yes -- individual-level parameter estimation using VBA toolbox (variational Bayesian) 5. **Check parameter recovery:** No -- no parameter recovery analysis reported 6. **Check model recovery:** No -- no confusion matrix or model recovery analysis reported 7. **Fit real data and compare models:** Yes -- BMS with protected exceedance probability across multiple model comparison steps 8. **Validate the winning model:** Partial -- model predictions shown to converge on actual group cheating frequencies (Fig 3C), but no formal posterior predictive check 9. **Analyze the winning model:** Yes -- conformity parameter gamma analyzed across conditions, correlations with other parameters tested 10. **Report results transparently:** Partial -- no mention of shared data or code
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** unclear
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_bayesian
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_F_affective_moral
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_PE_signal
- tax_rr_param_social_weight
- tax_rr_primary_topic = moral_harm
- tax_rr_secondary_topic = norm_conformity
- tax_rr_topic_moral_harm
- tax_rr_topic_norm_conformity
- tax_topic_moral_harm
- tax_topic_norm_conformity
