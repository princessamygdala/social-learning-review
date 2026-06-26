# Barnby et al. (2024)

- **study_id:** `a22a39917d0dd8ed8_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Barnby, J. M., Bell, V., Deeley, Q., Mehta, M. A., & Moutoussis, M. (2024). D2/D3 dopamine supports the precision of mental state inferences and self-relevance of joint social outcomes. *Nature Mental Health*, *2*, 562–573. https://doi.org/10.1038/s44220-024-00220-6
- **citation_short:** Barnby et al. (2024)
- **doi:** 10.1038/s44220-024-00220-6
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** Department of Neuroimaging, Institute of Psychiatry, Psychology & Neuroscience, University of London, London, UK; UCL Centre for Computational Psychiatry and Ageing, University College London, London, UK; Department of Psychology, Royal Holloway, University of London, London, UK; Centre for Human Neuroimaging, University College London, London, UK; College London, Cultural and Social Neuroscience Group,; University College London, London, UK; emails: joseph.barnby@rhul.ac.uk
- **code_url:** https://github.com/josephmbarnby/

## Computational level
- **study_focus:** Mentalizing learning / mental state inference under dopaminergic manipulation — how D2/D3 antagonism (haloperidol) alters computational mechanisms governing attributions of harmful intent and self-interest during iterative social observation.
- **study_focus_short:** Mentalizing learning / mental state inference under dopaminergic manipulation
- **learning_mode_description:** - Learning mode: Learning from partner's sharing decisions about partner's harmful intent and self-interest motivations   - Learning from:     - Source type (social): other (Dictator partner)     - Source content (social): action/policy (fair/unfair monetary split)   - Learning about:     - Target type (social): other (Dictator partner)     - Target content (social): state (mental state; harmful intent and self-interest motivations)
- **task_description:** Participants played a within-subjects, multi-trial Dictator game ("The Sharing Game") against three types of partner (fair, partially fair, unfair) over 6 trials each, under placebo, haloperidol (3 mg), and L-DOPA (150 mg) in a double-blind crossover design. After each trial, participants rated (1-100) the degree to which the partner was motivated by self-interest and by harmful intent.
- **task_paradigm:** Dictator game
- **players:** Single agent (participant), multi-target (3 Dictator partners: fair, partially fair, unfair)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Cartoon avatars with neutral expressions, monetary outcomes (fair split = £0.05 each vs. unfair = partner takes £0.10), numeric rating scales (1-100)
- **method:** pharmacological / behavioural
- **method_full:** Behavioural (pharmacological: double-blind, placebo-controlled, within-subjects crossover with haloperidol, L-DOPA, placebo)
- **main_result:** - Haloperidol increased learning rate from recent encounters (η; mean diff. = 0.15, 95% HDI: 0.03, 0.26; d = 0.66, 95% HDI: 0.22, 1.10) - Haloperidol increased impact of partner behaviour on harmful intent attributions (w_HI; mean diff. = 0.10, 95% HDI: 0.06, 0.13; d = 1.20, 95% HDI: 0.64, 1.75) - Haloperidol shifted policy intercept towards 0 (w_0; mean diff. = 0.58, 95% HDI: 0.01, 1.10; d = 0.43, 95% HDI: 0.02, 0.82) — note: within ROPE, treat with caution - Haloperidol induced negative coupling between harmful intent and self-interest attributions (mean diff. = -0.26, 95% CI: -0.32, -0.20; d = 2.22, 95% HDI: 1.22, 3.24) - w_HI reduced precision of harmful intent attributions (β = -6.13, 95% CI: -6.28, -5.97; effect size = -0.88, 95% CI: -0.92, -0.85) - Two-factor model discriminated drug conditions with mean accuracy = 0.86 (AUC = 0.91, sensitivity = 0.80, specificity = 0.78) - Factor 1 (flexibility) discriminated conditions (d = 0.94, 95% HDI: 0.35, 1.59); Factor 2 (learning) discriminated conditions (d = 1.23, 95% HDI: 0.64, 1.84) - Haloperidol had no significant effect on pHI_0, pSI_0, u_Pri, w_SI, or u_π
- **effect_size:** - Haloperidol increased learning rate from recent encounters (η; mean diff. = 0.15, 95% HDI: 0.03, 0.26; d = 0.66, 95% HDI: 0.22, 1.10) - Haloperidol increased impact of partner behaviour on harmful intent attributions (w_HI; mean diff. = 0.10, 95% HDI: 0.06, 0.13; d = 1.20, 95% HDI: 0.64, 1.75) - Haloperidol shifted policy intercept towards 0 (w_0; mean diff. = 0.58, 95% HDI: 0.01, 1.10; d = 0.43, 95% HDI: 0.02, 0.82) — note: within ROPE, treat with caution - Haloperidol induced negative coupling between harmful intent and self-interest attributions (mean diff. = -0.26, 95% CI: -0.32, -0.20; d = 2.22, 95% HDI: 1.22, 3.24) - w_HI reduced precision of harmful intent attributions (β = -6.13, 95% CI: -6.28, -5.97; effect size = -0.88, 95% CI: -0.92, -0.85) - Two-factor model discriminated drug conditions with mean accuracy = 0.86 (AUC = 0.91, sensitivity = 0.80, specificity = 0.78) - Factor 1 (flexibility) discriminated conditions (d = 0.94, 95% HDI: 0.35, 1.59); Factor 2 (learning) discriminated conditions (d = 1.23, 95% HDI: 0.64, 1.84) - Haloperidol had no significant effect on pHI_0, pSI_0, u_Pri, w_SI, or u_π
- **learning_from:** Other (Dictator partner); partner's fair/unfair monetary split actions
- **learning_about:** Other (Dictator partner); partner's harmful intent and self-interest motivations (mental states)  ---  ### 3. ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Bayesian belief updating (Model 3): separate likelihood weights for HI and SI attributions (w_HI, w_SI), shared prior uncertainty (u_Pri), 8 free parameters: {pHI_0, pSI_0, u_Pri, w_0, w_HI, w_SI, u_π, η}
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** 1. Model 1 (M1): Separate uncertainties AND separate likelihood weights for each attribution dimension. n_params = 9. (Full model from Barnby et al., 2022) 2. Model 2 (M2): Separate uncertainties but single shared likelihood weight (w). n_params = 7. 3. Model 3 (M3): Single shared prior uncertainty (u_Pri) but separate likelihood weights (w_HI, w_SI). n_params = 8.
- **model_mb_mf:** Bayesian (not RL; N/A for MB/MF distinction)
- **model_params:** - pHI_0: Prior magnitude for harmful intent [S] - pSI_0: Prior magnitude for self-interest [S] - u_Pri: Shared uncertainty over both attribution priors [S] - w_0: Intercept of likelihood matrix (calibrates magnitude of attributional change) [S] - w_HI: Impact of partner behaviour on harmful intent beliefs (belief flexibility for HI) [S] - w_SI: Impact of partner behaviour on self-interest beliefs (belief flexibility for SI) [S] - u_π: Consistency with which partner believed to act in accordance with their character [S] - η: Mixture of prior vs. posterior beliefs at partner change points (between-partner learning) [S]  Note: All parameters are social as they govern inferences about others' mental states. Mean fitted values not reported in a consolidated table (individual-level parameter estimates available via GitHub).
- **social_param:** w_HI (impact of partner behaviour on harmful intent attributions — the key parameter modulated by haloperidol, d = 1.20); η (between-partner learning rate, d = 0.66)
- **social_param_name:** w_HI
- **social_param_value:** 1.20
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Bayesian model selection via HBI (Hierarchical Bayesian Inference) — exceedance probability and model frequency at group and individual levels.
- **how_model_fit:** Individual-level fit via Hierarchical Bayesian Inference (HBI) algorithm (Piray et al., 2019), fitted independently per drug condition. Parameters estimated in native space with broad priors (μ_m = 0, σ_m = 6.5).
- **data_type_fit_to:** Self-report ratings (trial-by-trial attributions of harmful intent and self-interest, scale 1-100)  ---  ### 4. IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A (no neuroimaging)  ---  ### 5. PAPER QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 28 healthy males (from 86 phone-screened, 35 fully screened, 30 recruited, 2 dropped out); age mean = 29.21, SD = 8.61; within-subjects crossover (each participant in all 3 drug conditions)
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low-moderate. The Dictator game is a simplified economic game with cartoon avatars and binary outcomes (fair/unfair split). Partners follow pre-programmed policies (not real-time interaction). Pharmacological manipulation is well-controlled but the social interaction is minimal and stylized. The task does not capture real-world complexity of social inference.
- **eligibility_flag:** 
- **concerns:** - Male-only sample limits generalizability - Small sample (N = 28) for a pharmacological crossover - No non-social control condition — cannot determine whether haloperidol effects are specific to social inference vs. general belief updating - Partners are pre-programmed (not real); limited social interactivity - L-DOPA showed no behavioural effects, possibly due to insufficient dose or non-specific binding - Behavioural data previously published in Barnby et al. (2020) — this is a computational re-analysis of the same dataset. Potential overlap with Barnby et al. (2020, Translational Psychiatry) should be checked for duplicate flagging. - w_0 effect size within ROPE — authors note this should be treated with caution
- **limitations_reported:** Did not use a patient population, findings may not generalize to persecutory delusions; only included males to avoid hormonal heterogeneity, must be addressed in future; no non-social comparator to assess domain-specificity of haloperidol effects; design does not probe generalization of social knowledge outside game-theoretic task; l-DOPA showed no effect possibly due to insufficient dose or non-specific postsynaptic binding
- **limitations_categorized:** Limited generalizability (healthy males only); sample homogeneity (males only); no non-social control; limited ecological validity; task simplicity; null pharmacological condition (L-DOPA)
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 10
- **wc_total:** 10.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - effect_size for w_0: MEDIUM — authors note posterior within ROPE, should be treated with caution - preregistered: MEDIUM — the original behavioural experiment was preregistered; this computational analysis may not have been preregistered separately
- **cannot_find:** - Mean fitted parameter values per condition (not reported in consolidated table; available via GitHub) - Exact number of free parameters for M1 explicitly stated (inferred as 9 from model description: separate u_HI + u_SI instead of shared u_Pri = +1 param vs. M3)
- **other_notes:** - This is a computational re-analysis of behavioural data from Barnby et al. (2020, Translational Psychiatry). The original publication reported descriptive behavioural results; this paper applies formal computational models. Should be checked against Barnby et al. (2020) for duplicate data flagging. - Previous work (Barnby et al., 2020; 2022) used the same model framework to study trait paranoia; this paper extends to pharmacological manipulation. - The HBI algorithm (Piray et al., 2019) is used rather than standard EM or MCMC for model fitting. - All 8 parameters in the winning model are inherently social as they govern mental state inference about others.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pharma_dopamine
- pop_healthy_adults
- rr_pharma_dopamine
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_mentalizing_inference
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_mod_active_interaction
- tax_mod_mentalizing_inference
- tax_model_MB
- tax_model_MF
- tax_model_bayesian
- tax_param_learning_rate
- tax_param_social_bonus
- tax_popclass_healthy
- tax_popclass_pharmacological
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_learning_rate
- tax_rr_param_precision
- tax_rr_primary_topic = mentalizing
- tax_rr_secondary_topic = reputation_learning
- tax_rr_topic_mentalizing
- tax_rr_topic_reputation_learning
- tax_topic_mentalizing
- tax_topic_reputation_learning
