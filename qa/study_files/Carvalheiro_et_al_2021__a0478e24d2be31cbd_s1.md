# Carvalheiro et al. (2021)

- **study_id:** `a0478e24d2be31cbd_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Carvalheiro, J., Conceicao, V. A., Mesquita, A., & Seara-Cardoso, A. (2021). Acute stress impairs reward learning in men. *Brain and Cognition, 147*, 105657. https://doi.org/10.1016/j.bandc.2020.105657
- **citation_short:** Carvalheiro et al. (2021)
- **doi:** 10.1016/j.bandc.2020.105657
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** lableonline17December2020; lable at ScienceDirect; emails: ana.searacardoso@psi.uminho.pt, ana.mesquita@psi.uminho.pt, vasco.conceicao7@gmail.com
- **code_url:** 

## Computational level
- **study_focus:** Reward and punishment learning under acute stress; effect of acute stress on prediction-error-driven reinforcement learning.
- **study_focus_short:** Reward and punishment learning under acute stress
- **learning_mode_description:** - Learning mode: Learning from one's own monetary outcomes (gains/losses) about stimulus-action values under stress vs. control   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (monetary gains/losses)   - Learning about:     - Target type (non-social): world (stimulus-action values)     - Target content (non-social): action/policy (which stimulus to choose to maximize reward / minimize punishment)
- **task_description:** Participants completed a reinforcement-learning task with pairs of abstract stimuli associated with probabilistic monetary gains (win 0.50 EUR or nothing), losses (lose 0.50 EUR or nothing), or neutral outcomes, choosing between two stimuli on each trial to maximize payoffs, while exposed to an acute auditory stressor (uncontrollable alarm sound) or a control condition in alternating blocks.
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), no social partner.
- **n_players:** single agent (1)
- **partner_type:** none
- **stimuli:** Abstract visual stimuli (fractal-like), monetary outcomes (0.50 EUR gain/loss/neutral), auditory alarm stressor.
- **method:** behavioural
- **method_full:** Behavioural (+ skin conductance for manipulation check)
- **main_result:** - Acute stress impaired choice performance toward monetary gains but not losses (condition x valence interaction: beta = -0.19, p = .018, 95% CI [-0.34, -0.032]) - Stress reduced learning rate for positive prediction errors (alpha+: stress M = 0.40 vs. control M = 0.51; t(61) = -2.25, p = .028, d = -0.29, 95% CI [-0.21, -0.013]) - No effect of stress on learning rate for negative prediction errors (alpha-: t(61) = -0.72, p = .47, d = -0.092) - No effect of stress on inverse temperature beta (t(61) = -0.016, p = .99, d = 0.002) - Stress reduced alpha+ x beta product (t(61) = -2.58, p = .012, d = -0.33, 95% CI [-2.04, -0.26]) with significant condition x valence interaction (F(1,61) = 4.85, p = .032, eta-squared = 0.074) - Manipulation check: self-reported stress higher in stress condition (F(1,61) = 107.67, p < .001, eta-squared = 0.64; d = 1.32); SCR rate higher (F(1,57) = 20.61, p < .001, eta-squared = 0.27; d = 0.57)
- **effect_size:** 
- **learning_from:** Self; own monetary outcome (reward/punishment feedback)
- **learning_about:** World; stimulus-action values (which abstract stimulus leads to better outcomes)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** RW with dual learning rates (alpha+, alpha-; 1 beta). Q_A(t+1) = Q_A(t) + alpha * delta(t), where delta(t) = r(t) - Q_A(t), alpha = alpha+ if delta > 0, alpha- if delta < 0. Softmax: P_A(t) = exp[Q_A(t)*beta] / (exp[Q_A(t)*beta] + exp[Q_B(t)*beta]). Fitted values: alpha+ stress M = 0.40, control M = 0.51; alpha- stress M = 0.25, control M = 0.27; beta stress M = 9.52, control M = 9.53.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "Double-alpha RW (Frank et al., 2007)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "BIC, AIC, random-effects Bayesian model comparison (PEP)"} 2. {"name": "Single-alpha Q-learning (standard RW)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BIC, AIC, random-effects Bayesian model comparison (PEP)"}
- **model_mb_mf:** MF
- **model_params:** - alpha+ : learning rate for positive prediction errors. Stress M = 0.40 (SEM = 0.033), Control M = 0.51 (SEM = 0.038) - alpha- : learning rate for negative prediction errors. Stress M = 0.25 (SEM = 0.025), Control M = 0.27 (SEM = 0.027) - beta : inverse temperature (decision noise). Stress M = 9.52 (SEM = 0.49), Control M = 9.53 (SEM = 0.51)
- **social_param:** None. No social parameters in this model.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC, AIC, random-effects Bayesian model comparison (protected exceedance probabilities), Bayesian model averaging. Results were inconclusive between BIC and AIC: BIC favored single-alpha in stress (PEP = 0.96) but was inconclusive in control; AIC favored double-alpha in control (PEP = 0.995) but inconclusive in stress. Authors used Bayesian model averaging to combine estimates across both models, which replicated the key findings.
- **how_model_fit:** Individual-level fit. Maximum a posteriori (MAP) estimation with Beta(1.1, 1.1) priors on learning rates and Gamma(1.2, 5) prior on inverse temperature; fmincon with 100 random starting points minimizing negative log posterior.
- **data_type_fit_to:** Choice behavior (trial-by-trial binary choices)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 62 healthy males; age range 18-35 years (M = 21.9, SD = 3.7). N = 58 for SCR analyses (4 excluded for poor signal quality). 3 participants performed below chance and sensitivity analyses were run excluding them.
- **population_category:** healthy adults
- **population_age_range:** 18–35
- **ecological_validity:** Low-moderate. Standard lab-based probabilistic reinforcement learning task with abstract stimuli and small monetary outcomes. Stress manipulation uses uncontrollable alarm sound, which is somewhat ecologically valid as an acute stressor but artificial in its pairing with the task. Male-only sample limits generalizability.
- **eligibility_flag:** The task is non-social. Learning does not occur in a social context. The stressor is an auditory alarm, not a social stressor. Flag: "Non-social learning task; no social context for learning. Stress manipulation is non-social (auditory alarm). Does not meet inclusion criterion for social context.
- **concerns:** - Model comparison between double-alpha and single-alpha models was inconclusive (BIC and AIC disagreed); authors resorted to Bayesian model averaging rather than definitively selecting a winning model. - The condition x valence interaction on learning rates was not significant in the full sample (F(1,61) = 2.13, p = .15); it only reached significance after excluding 3 below-chance participants (F(1,58) = 4.61, p = .036). The paired t-tests on alpha+ were reported despite lacking a significant interaction, which the authors acknowledged was "not formally well-justified." - Male-only sample limits generalizability. - Potential confound between stress and distraction from auditory stressor, though authors argue against this.
- **limitations_reported:** Potential confound between stress induction and distraction due to auditory stressor used during the task; steps taken to minimize unpredictability of stressor may not fully eliminate distraction; only male participants included due to menstrual-cycle-dependent variations in stress responsivity and reward/punishment learning; further studies needed to assess whether acute stress has same computational effects on reward and punishment learning in men and women.
- **limitations_categorized:** Potential confound (stress vs. distraction); limited generalizability (male-only sample); limited ecological validity (lab task with abstract stimuli).
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `eligibility_flag`: HIGH confidence — this is a non-social learning task. No social agent, no social context for learning. The stressor is a non-social auditory alarm. - `social_param`: N/A — no social parameters because no social component. - `model comparison outcome`: MEDIUM — model comparison was inconclusive; BMA used as workaround. - `wc_3` (simulate): MEDIUM — parameter recovery was done but unclear if task was simulated before fitting. - `wc_10` (report transparently): MEDIUM — no explicit mention of data/code sharing.
- **cannot_find:** - Data/code availability statement not found in the text. - No information on preregistration.
- **other_notes:** This paper studies how acute stress affects reward vs. punishment learning using a purely non-social reinforcement learning paradigm. The stressor is an auditory alarm (non-social). There is no social agent, no social information source, and no social learning target. This paper does not belong in a review of computational models of social learning unless the review's scope includes non-social learning as a comparison/control category. The computational modeling is solid (RW with dual learning rates), with good parameter recovery and model validation, but the model comparison itself was inconclusive.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- pop_stress
- rr_pop_healthy_adults
- rr_pop_stress
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = general
- spec_locus = source
- tax_domain_G_uncertainty_volatility
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = G_uncertainty_volatility
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = volatility
- tax_rr_topic_volatility
- tax_topic_volatility
