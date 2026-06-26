# Harada (2023)

- **study_id:** `a02c7c89a2ee718ad_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Harada, T. (2023). Exploring the effects of risk-taking, exploitation, and exploration on divergent thinking under group dynamics. *Frontiers in Psychology*, *13*, 1063525. https://doi.org/10.3389/fpsyg.2022.1063525
- **citation_short:** Harada (2023)
- **doi:** 10.3389/fpsyg.2022.1063525
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Behavioural economics / Economics
- **affiliations_raw:** mpirical studies reported that and cognitive ones because the cognitive processes derive from; School of Business Administration, Kobe University, Kobe, Japan; University Bremen, Tsutomu Harada *; University Graduate School of; section of the journal; mitted which does not; University of Warsaw,; Schooler et al; emails: harada@people.kobe-u.ac.jp
- **code_url:** 

## Computational level
- **study_focus:** Creativity/divergent thinking — examining how risk attitudes and the exploitation/exploration trade-off (estimated via Q-learning on a two-armed bandit task) relate to divergent thinking performance across individuals, dyads, and triads.
- **study_focus_short:** Creativity/divergent thinking
- **learning_mode_description:** - Learning mode: Learning from reward outcomes in a two-armed bandit task; parameters estimated from this task are then correlated with divergent thinking scores.   - Learning from:     - Source type (non-social for individuals; joint for dyads/triads): self (individuals) / group (dyads, triads)       - Dyads and triads: marked as **joint** (collective decision-making)     - Source content (non-social): outcome (reward feedback: +10 or -10 points)   - Learning about:     - Target type (non-social): world (which bandit arm yields higher reward)     - Target content (non-social): action/policy (optimal choice strategy; exploitation vs. exploration trade-off)
- **task_description:** Participants (as individuals, dyads, or triads) completed an Alternative Use Test (AUT) measuring divergent thinking and a two-armed bandit (TAB) task where they chose between two boxes across 100 trials to maximize rewards (+10 or -10 points), with reward probabilities switching twice. Q-learning parameters from the TAB were then regressed on AUT scores.
- **task_paradigm:** Two-armed bandit
- **players:** Single agent (individual, N=78), multi-agent dyads (N=85 dyads, 170 participants), multi-agent triads (N=61 triads, 183 participants)
- **n_players:** network (5+)
- **partner_type:** human (live)
- **stimuli:** Two boxes (two-armed bandit) with binary reward outcomes (+10 or -10 points); three common objects (shoes, buttons, keys) for the AUT
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - For individuals: risk-seeking for gains (μ: β = -10.47, p < 0.01), risk aversion for losses (ν: β = -15.02, p < 0.01), exploitation (inverse temperature β: coefficient = 1.13, p < 0.05), and loss aversion (λ: β = 8.26, p < 0.01) significantly predicted divergent thinking   - For dyads: no significant effects of risk attitudes or inverse temperature on divergent thinking; loss aversion negatively related (λ: β = -6.73, p < 0.05); positive learning rate significant (α+: β = 11.63, p < 0.01)   - For triads: risk aversion for gains (μ: β = 16.02, p < 0.01), risk aversion for losses (ν: β = -13.66, p < 0.01), and exploration (inverse temperature β: coefficient = -0.83, p < 0.10) significantly predicted divergent thinking; negative learning rate significant (α−: β = -14.20, p < 0.01)   - TAB performance (learning efficiency) positively predicted divergent thinking across all group sizes (individuals: β = 0.16, p < 0.10; dyads: β = 0.24, p < 0.05; triads: β = 0.52, p < 0.01)   - Triads outperformed individuals and dyads on divergent thinking (mean AUT: triads = 67.56, dyads = 49.02, individuals = 53.54; Kruskal-Wallis χ² = 7.15, p = 0.03)   - Note: Only Poisson regression coefficients and p-values reported; no standardized effect sizes (Cohen's d, r², η²) provided
- **effect_size:** - Main Results:   - For individuals: risk-seeking for gains (μ: β = -10.47, p < 0.01), risk aversion for losses (ν: β = -15.02, p < 0.01), exploitation (inverse temperature β: coefficient = 1.13, p < 0.05), and loss aversion (λ: β = 8.26, p < 0.01) significantly predicted divergent thinking   - For dyads: no significant effects of risk attitudes or inverse temperature on divergent thinking; loss aversion negatively related (λ: β = -6.73, p < 0.05); positive learning rate significant (α+: β = 11.63, p < 0.01)   - For triads: risk aversion for gains (μ: β = 16.02, p < 0.01), risk aversion for losses (ν: β = -13.66, p < 0.01), and exploration (inverse temperature β: coefficient = -0.83, p < 0.10) significantly predicted divergent thinking; negative learning rate significant (α−: β = -14.20, p < 0.01)   - TAB performance (learning efficiency) positively predicted divergent thinking across all group sizes (individuals: β = 0.16, p < 0.10; dyads: β = 0.24, p < 0.05; triads: β = 0.52, p < 0.01)   - Triads outperformed individuals and dyads on divergent thinking (mean AUT: triads = 67.56, dyads = 49.02, individuals = 53.54; Kruskal-Wallis χ² = 7.15, p = 0.03)   - Note: Only Poisson regression coefficients and p-values reported; no standardized effect sizes (Cohen's d, r², η²) provided
- **learning_from:** World; binary reward outcomes (+10/-10) in two-armed bandit task. Source: self (individuals) / group (dyads, triads)
- **learning_about:** World; which bandit arm yields higher expected reward (optimal choice policy). Target: world  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** Q-learning with prospect utility function and asymmetric learning rates (α+, α−, μ, ν, λ, φ, β); 7 free parameters. Only one model tested — no model comparison performed.
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Q-learning with prospect utility", "family": "Q-learning", "n_params": 7, "metric": "N/A — single model, no comparison"}]
- **model_mb_mf:** MF
- **model_params:** - α+ (positive learning rate): mean = 0.47 (pooled); bounded [0, 1]; beta prior - α− (negative learning rate): mean = 0.48 (pooled); bounded [0, 1]; beta prior - μ (risk aversion parameter for gains): mean = 0.54 (pooled); non-negative; gamma prior [S — when applied to group decision-making in dyads/triads] - ν (risk-seeking parameter for losses): mean = 0.49 (pooled); non-negative; gamma prior [S — when applied to group decision-making] - λ (loss aversion): mean = 0.50 (pooled); non-negative; gamma prior [S — when applied to group decision-making] - β (inverse temperature; exploitation/exploration ratio): mean = 2.53 (pooled); non-negative; gamma prior [S — when applied to group decision-making] - φ (autocorrelation control): mean = -5.61 (pooled); unbounded
- **social_param:** No explicitly social parameter in the model. The same Q-learning model is applied to individual, dyadic, and triadic group behavior without a dedicated social parameter. The group-level application means all parameters implicitly reflect collective decision-making in dyads/triads, but no parameter specifically models social influence.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** N/A — only one model tested; no model comparison performed
- **how_model_fit:** individual-level-fit (MAP estimation per subject/group)
- **data_type_fit_to:** choice behavior (binary choices in two-armed bandit)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A — no neuroimaging
- **key_regions:** N/A — no neuroimaging
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 431 total (171 female); 78 individuals, 170 participants in 85 dyads, 183 participants in 61 triads; age range 18–20 (mean = 18.92, SD = 0.77)
- **population_category:** healthy adults
- **population_age_range:** 18–20
- **ecological_validity:** Low ecological validity. Creativity measured by a timed lab test (AUT) with common objects. Learning measured by a standard two-armed bandit with abstract reward feedback. No real social interaction structure specified for group decision-making (communication protocol not described). The relationship between Q-learning parameters and divergent thinking is correlational (regression), not causal.
- **eligibility_flag:** FLAGGED — Borderline eligibility. The computational model (Q-learning) is fit to a bandit task, and parameters are then correlated with creativity scores from a separate task (AUT). The learning in the bandit task is non-social for individuals; for dyads/triads, the "social" element is collective decision-making on bandit choices, but the paper does not model social learning processes (e.g., learning about or from others). The study focus is creativity/divergent thinking, not social learning per se. The computational model does not incorporate any social learning mechanism. This is better characterized as a study of individual reinforcement learning parameters applied to group decision-making, with creativity as the outcome variable.
- **concerns:** - Only one model tested — no model comparison, which significantly limits interpretability - No standardized effect sizes reported (only Poisson regression coefficients and p-values) - The Q-learning model is applied identically to individuals, dyads, and triads, treating group choices as if made by a single agent — no explicit multi-agent modeling or social influence mechanism - Communication protocol for dyads/triads during the TAB is not described - The relationship between TAB parameters and AUT scores is purely correlational - No parameter recovery or model recovery reported - No model simulations described - No posterior predictive checks - AUT scored by only 2 raters (though ICC reported) - Paper uses α and ν notation inconsistently (describes "risk-seeking in losses" for ν but the parameter actually controls the shape of the loss utility function)
- **limitations_reported:** Results may not generalize across cultural and generational backgrounds; sample limited to narrow age range (18–20 years) and divergent thinking changes with age; results depend on specific creativity task (AUT) and learning task (TAB); AUT alone is not sufficient for measuring creativity as it consists of convergent and divergent thinking; learning properties measured through TAB are task-specific
- **limitations_categorized:** Limited generalizability (cultural/demographic); limited age range; task specificity; construct validity (AUT as creativity measure); task-specific learning parameters
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 3.5
- **wc_total:** 3.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `social_param`: LOW — no explicitly social parameter in the model; the "social" element is only that dyads/triads make collective choices - `eligibility_flag`: MEDIUM — borderline social learning; the Q-learning model treats groups as single agents with no social learning mechanism - `learning_mode`: MEDIUM — the learning in the bandit task is essentially non-social; the social context is only in group decision-making, not in what is learned or the learning mechanism - `effect_size`: LOW — no standardized effect sizes; only unstandardized Poisson regression coefficients reported - `model_comparison_metric`: HIGH — explicitly N/A, only one model tested
- **cannot_find:** - Standardized effect sizes (Cohen's d, r², η², etc.) — not reported - Communication protocol for dyadic/triadic group decision-making in the TAB - Model comparison (only one model used) - Supplement not available (none found) - Parameter recovery results - Model simulation results
- **other_notes:** This paper is by the same author (Harada) who published related work in 2020 and 2021 on the same topic (risk-taking and creativity using Q-learning). The 2020 paper (Harada, 2020 in PLoS ONE) focused on individuals only. This paper extends to dyads and triads. Should check for potential duplicate/overlapping data with those papers — the individual sample (N=78) may overlap. The paper is published in Frontiers in Psychology (Decision Neuroscience section). The Q-learning model with prospect utility function was originally proposed by Harada (2020). This is fundamentally a study of how RL parameters from a non-social task predict creativity scores, with group dynamics as a moderator — it is not a study of social learning in the traditional computational psychiatry sense.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- tax_domain_G_uncertainty_volatility
- tax_mod_active_interaction
- tax_mod_experiential
- tax_model_MF
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_temperature
- tax_popclass_healthy
- tax_rr_domain = G_uncertainty_volatility
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_temperature
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = exploration_exploitation
- tax_rr_topic_exploration_exploitation
- tax_social_nonsocial_comparison
- tax_topic_exploration_exploitation
