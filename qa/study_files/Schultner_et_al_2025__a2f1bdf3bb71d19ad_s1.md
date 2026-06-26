# Schultner et al. (2025)

- **study_id:** `a2f1bdf3bb71d19ad_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Schultner, D., Molleman, L., & Lindström, B. (2025). Feature-based reward learning shapes human social learning strategies. *Nature Human Behaviour*, *9*, 2183–2198. https://doi.org/10.1038/s41562-025-02269-4
- **citation_short:** Schultner et al. (2025)
- **doi:** 10.1038/s41562-025-02269-4
- **publication_type:** peer-reviewed journal
- **year:** 2025.0
- **field_of_study:** Anthropology / Cultural evolution
- **affiliations_raw:** Department of Clinical Neuroscience, Karolinska Institutet, Stockholm, Sweden; Department of Psychology, University of Amsterdam, Amsterdam,; mpirical findings challenge the view that these; ething tastes) and social; mpirical suppor; ether28,29; etherlands; emails: bjorn.lindstrom@ki.se, david.schultner@ki.se
- **code_url:** https://osf.io/jry9x/

## Computational level
- **study_focus:** Social learning strategies — how individuals learn to use social features (others' choices, payoffs, age, success) as predictors of their own rewards, giving rise to social learning strategies such as copy-the-majority and payoff-biased learning.
- **study_focus_short:** Social learning strategies
- **learning_mode_description:** - Learning mode: Learning from one's own reward outcomes, in the presence of social features (others' choices, payoffs), about the predictive value of social and non-social environmental features for reward.   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (binary reward feedback)   - Learning about:     - Target type (social): other (group of demonstrators)       - Target content (social): action/policy (others' choices) and outcome (others' payoffs) as predictive features     - Target type (non-social): world       - Target content (non-social): stimulus (colour/option features) as predictive features
- **task_description:** Participants repeatedly chose between colour-coded options in a probabilistic bandit task, receiving binary reward feedback. Social features (others' choices or others' payoffs from ostensible previous participants) were displayed alongside options; the alignment between social features and reward varied by condition (congruent vs. incongruent), followed by a test phase with novel options to assess transfer of learned social feature weights.
- **task_paradigm:** Stereotype learning task
- **players:** Single agent (participant), multi-target (100 computer-simulated demonstrators)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Coloured squares (non-social features), bar charts showing others' choices or others' payoffs (social features), binary reward feedback
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Exp 1: Social learning sharply differed by condition; 92% congruent participants followed majority on first test trial vs. 30% incongruent (logistic regression: β = −3.33, s.e. = 0.37, z = −8.89, p < 0.001, 95% CI [−3.92, −2.61]) - Exp 2: Payoff-biased social learning shaped by experience (between-condition difference: β = −3.98, s.e. = 0.55, z = −7.30, p < 0.001, 95% CI [−5.06, −2.90]) - Exp 3: Only reward-predictive social feature guided test-phase choices (β = 1.54, s.e. = 0.25, z = 6.15, p < 0.001, 95% CI [1.05, 2.03]) - Exp 4: Four-option bandit replicated results; congruent participants chose majority option 73% vs. 14% incongruent (β = 2.86, s.e. = 0.33, z = 8.6, p < 0.001, 95% CI [2.21, 3.51]) - Exp 5: Congruent participants 29% more susceptible to social influence in BEAST task (W = 21,150, p = 0.004, 95% CI [0.02, 0.12]); estimated social feature weight predicted individual differences in social influence (robust regression: β = 0.2, s.e. = 0.07, t = 2.72, p = 0.007, 95% CI [0.06, 0.35]) - Exp 6: Feature competition confirmed — participants preferred single-condition colour in high-value pair (β = 0.618, s.e. = 0.14, z = 4.59, p < 0.001, 95% CI [0.34, 0.89]) - Model comparison: SFL model best account across all 6 experiments (protected exceedance probability = 1 in-sample; 0.81 out-of-sample) - Agent-based simulations: SFL model reproduces emergence of copy-the-majority, payoff bias, age bias, and success bias strategies across temporal, spatial, dangerous, and competitive environments
- **effect_size:** - Exp 1 between-condition first test trial: β = −3.33 (unstandardized logistic regression coefficient) - Exp 2 between-condition first test trial: β = −3.98 - Exp 3 across conditions: β = 1.54 - Exp 4 majority choice between-condition: β = 2.86 - Exp 5 social influence difference: W = 21,150 (Wilcoxon); feature weight predicting influence: β = 0.2 - Exp 6 high-value pair feature competition: β = 0.618
- **learning_from:** Self; own binary reward outcomes experienced after choosing among options presented with social features (others' choices or payoffs)
- **learning_about:** Others (group of demonstrators); the predictive value of social features (others' choices, payoffs) for own rewards — i.e., learning which social features reliably predict reward  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** SFL + prior (Q-learning with linear function approximation; 3 params: α, β, P)  Full specification: - Q(s, a) = Σ_i s_i × w_i (linear combination of feature values and weights) - Choice: softmax P(s, a_i) = exp(Q(s, a_i)/β) / Σ_j exp(Q(s, a_j)/β) - Weight update: w_{t+1} = w_t + α(R_t − Q(s, a)) × x(a_t) (Rescorla-Wagner / gradient descent on feature weights) - Prior parameter P sets initial value of social feature weight w_others
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "SFL", "family": "Rescorla-Wagner with linear function approximation", "n_params": 2, "metric": "AIC / protected exceedance probability"},   {"name": "SFL + prior", "family": "Rescorla-Wagner with linear function approximation", "n_params": 3, "metric": "AIC / protected exceedance probability"},   {"name": "SFL (separate α)", "family": "Rescorla-Wagner with linear function approximation", "n_params": 3, "metric": "AIC / protected exceedance probability"},   {"name": "Fixed Heuristics (decision biasing)", "family": "Q-learning + fixed social weight", "n_params": 4, "metric": "AIC / protected exceedance probability"},   {"name": "Value Shaping", "family": "Q-learning + social pseudo-reward", "n_params": 3, "metric": "AIC / protected exceedance probability"},   {"name": "Value Shaping + prior", "family": "Q-learning + social pseudo-reward", "n_params": 4, "metric": "AIC / protected exceedance probability"} ]
- **model_mb_mf:** MF
- **model_params:** - α (learning rate) [0 ≤ α ≤ 1]: governs weight update magnitude - β (softmax temperature) [β > 0]: governs exploration vs. exploitation - P (prior weight) [S]: initial value of social feature weight w_others; captures pre-experimental bias toward social information - w_others [S] (learned, not free): weight of social feature (others' choices), learned through experience - w_payoff [S] (learned, not free): weight of social feature (others' payoffs), learned through experience - w_colour (learned, not free): weight of non-social feature  Fitted parameter values (from Supplementary Table S1, Experiment 1 median): Not directly available in extracted text; paper states parameters were estimated via MLE individually per participant and median values from Exp 1 used for out-of-sample predictions. Simulation parameters for ABM: α = 0.2, β = 0.1. A priori simulation ranges: α = U(0.001, 0.4), β = U(0.0001, 0.2), P = U(0, 0.2).
- **social_param:** P (prior weight) [S] — initial value of social feature weight, capturing pre-experimental bias toward social information; w_others [S] — learned weight of others' choices feature; w_payoff [S] — learned weight of others' payoffs feature. These social parameters are not structurally distinct from non-social weights; they emerge from the same learning mechanism applied to social features.
- **social_param_name:** P
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC (individual-level), with Bayesian random-effects model comparison (protected exceedance probability). Out-of-sample prediction using generalization criterion method (log-likelihood from Exp 1 parameters applied to Exps 2–6).
- **how_model_fit:** individual-level-fit (maximum likelihood estimation with 20 random starting points per participant)
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Total N = 1,941 (Exp 1: n = 285; Exp 2: n = 244; Exp 3: n = 362; Exp 4: n = 353; Exp 5: n = 388; Exp 6: n = 309). Ages: M = 33.8, SD = 11.96 across all experiments. 931 female, 957 male, 21 other. All recruited via Prolific, online.
- **population_category:** healthy adults
- **population_age_range:** M=33.8 (SD=11.96)
- **ecological_validity:** Low — simplified computerized bandit tasks with computer-generated "demonstrators" (deception); binary reward; no real social interaction. Authors acknowledge this limitation and call for naturalistic data in future work.
- **eligibility_flag:** 
- **concerns:** - Social agents are computer-simulated (not real participants); participants were deceived about this - All experiments are online with Prolific participants; no in-lab replication - The "social" features are functionally identical to any other environmental cue; the model makes no structural distinction between social and non-social features — this is the theoretical point but may limit claims about specifically *social* learning - Agent-based simulations use fixed parameter values (α = 0.2, β = 0.1) rather than empirically recovered distributions - No neural data collected
- **limitations_reported:** The SFL model focuses on observable social cues and does not address inferential forms of social learning important for teaching; simple linear feature representations were used rather than multidimensional or abstract features; experiments used simplified computerized tasks rather than naturalistic data; agent-based simulations did not cover the entire mosaic of social learning strategies; the model does not address scenarios with delayed rewards (though could be extended with temporal-difference learning); confirmatory developmental evidence would require intensive longitudinal studies of children's everyday social-reward environments
- **limitations_categorized:** limited ecological validity; task simplicity; limited model scope (no inferential social learning); simplified feature representations; limited generalizability (no naturalistic data); incomplete strategy coverage in simulations; no delayed reward scenarios tested
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 9
- **wc_total:** 9.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params fitted values: MEDIUM — exact fitted parameter values per experiment referenced as being in Supplementary Table S1 but specific numbers not fully extractable from the .txt conversion of the supplement (table rendered as image). The simulation parameters (α = 0.2, β = 0.1) and a priori ranges are reported. - effect_size format: MEDIUM — paper reports unstandardized logistic regression coefficients (β) and Wilcoxon W statistics rather than Cohen's d or r; these are the primary effect sizes reported.
- **cannot_find:** - Exact fitted parameter means/medians from Supplementary Table S1 (table likely rendered as image in supplement PDF; .txt extraction shows only the table caption)
- **other_notes:** - This is a behavioural-only paper (no neuroimaging) with a strong computational modelling component - The paper's key theoretical contribution is unifying multiple social learning strategies (copy-the-majority, payoff bias, age bias, success bias, copy-when-uncertain) under a single domain-general feature-based reinforcement learning mechanism - The "social" parameter is not structurally different from non-social parameters — the model treats all features identically; what makes a feature "social" is its content (others' choices/payoffs), not its computational treatment - Pre-registration links: Exp 1: https://aspredicted.org/H9P_YLD; Exp 2: https://aspredicted.org/HK1_BQQ; Exp 3: https://aspredicted.org/DCD_YB3; Exp 4: https://aspredicted.org/PKH_DL1; Exp 6: https://aspredicted.org/D6S_PMP - Data and code: https://osf.io/jry9x/
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_social_info_search
- spec_depth = general
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_mod_experiential
- tax_mod_social_info_search
- tax_model_MF
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_social_weight
- tax_param_temperature
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_topic_social_info_use
- tax_topic_social_info_use
