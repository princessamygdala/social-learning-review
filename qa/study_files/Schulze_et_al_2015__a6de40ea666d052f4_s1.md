# Schulze et al. (2015)

- **study_id:** `a6de40ea666d052f4_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Schulze, C., van Ravenzwaaij, D., & Newell, B. R. (2015). Of matchers and maximizers: How competition shapes choice under risk and uncertainty. *Cognitive Psychology*, *78*, 78--98. https://doi.org/10.1016/j.cogpsych.2015.03.002
- **citation_short:** Schulze et al. (2015)
- **doi:** 10.1016/j.cogpsych.2015.03.002
- **publication_type:** peer-reviewed journal
- **year:** 2015.0
- **field_of_study:** Psychology
- **affiliations_raw:** lableonline8April2015 tions seeking maximal profits, and athletes training to win, all; Schooler, 2008; Peterson & Ulehla, 1965; Wolford, Newman, Miller, & Wig, 2004),; CenterforAdaptiveRationality,MaxPlanckInstituteforHumanDevelopment,Lentzeallee; mited and uncertain information about the true random nature of a; SchoolofPsychology,UniversityofNewSouthWales,Sydney,Australia; SchoolofPsychology,UniversityofNewcastle,Newcastle,Australia; mited resources, scarcity and rivalry are central; mitedresourcesundernaturalcircumstances(e; emails: cschulze@mpib-berlin.mpg.de
- **code_url:** 

## Computational level
- **study_focus:** Competitive reinforcement learning; how competition with a computerized opponent shapes probability matching vs. maximizing in sequential binary choice under uncertainty.
- **study_focus_short:** Competitive reinforcement learning
- **learning_mode_description:** - Learning mode: Learning from competitive choice outcomes about optimal choice strategy under competition   - Learning from:     - Source type (social): other (computerized opponent)       - Joint: the outcome is **joint** -- reward depends on convergence/divergence of participant and opponent choices     - Source content (non-social): outcome (monetary payoff, which is jointly determined)   - Learning about:     - Target type (non-social): world (which option is more rewarding given opponent behavior)     - Target content (non-social): action/policy (optimal choice strategy -- matching vs. maximizing)
- **task_description:** Participants repeatedly chose between two options (light bulbs) over 500 trials, competing against a computerized opponent that either mimicked their strategy or was indifferent. Correct predictions earned 4 cents, split to 2 cents when both agents chose the same correct option; outcome probabilities (.70/.30) were unknown and learned from experience.
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), dyadic (computerized opponent; mimicry or indifferent)
- **n_players:** dyadic (2)
- **partner_type:** computer (algorithmic)
- **stimuli:** Two light bulbs (binary choice), monetary payoffs (0/2/4 cents), opponent choice feedback over 10-trial moving window
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Significant main effect of trial block on high-probability choices (F(4.90, 235.11) = 18.42, p < .001, $\eta^2_p$ = .277, BF = 2.79 x 10^22) - Significant main effect of competitor type on choice proportions (F(1, 48) = 11.66, p = .001, $\eta^2_p$ = .195, BF = 25.08) - Mimicry condition approached probability matching (M = .76 by final block); indifferent condition approached maximizing (M = .92 by final block) - Participants facing mimicry opponents were 2.17 times more likely to probability match; those facing indifferent opponents were 2.40 times more likely to maximize - All competitive RL models outperformed individual RL model: Individual RL vs. Payoff Comparison (BF = 6.50), vs. Goal Separation (BF = 24.66), vs. Strategy Avoidance (BF = 10.69)
- **effect_size:** $\eta^2_p$ = .277 (trial block), $\eta^2_p$ = .195 (competitor type), $\eta^2_p$ = .041 (interaction); OR = 2.17 (matching likelihood, mimicry), OR = 2.40 (maximizing likelihood, indifferent); BF = 25.08 (competitor type effect); BF = 6.50, 24.66, 10.69 (competitive models vs. individual RL)
- **learning_from:** Joint outcomes (monetary payoffs determined by own choice, opponent choice, and nature); Source: other (opponent) + world (nature)
- **learning_about:** Optimal choice policy (matching vs. maximizing) given opponent behavior; Target: world/action policy  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Competitive Strategy Avoidance RL (Model 4): $p_{t+1}(i) = (1 - \beta) \cdot \frac{e^{\theta \cdot q_t(i)}}{e^{\theta \cdot q_t(j)} + e^{\theta \cdot q_t(i)}} + \beta \cdot s_t(j)$; utility $u_t(i) = g_t(i)$ (accuracy); 3 params: $\alpha$, c (sensitivity), $\beta$ (competition weight). Note: best in Exp 1 numerically but not significantly better than other competitive models.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Stationary baseline", "family": "statistical", "n_params": 1, "metric": "AIC"},   {"name": "M1: Individual RL", "family": "Rescorla-Wagner", "n_params": 2, "metric": "AIC"},   {"name": "M2: Competitive Payoff Comparison", "family": "Rescorla-Wagner + inequity aversion", "n_params": 3, "metric": "AIC"},   {"name": "M3: Competitive Goal Separation", "family": "Rescorla-Wagner + dual-goal utility", "n_params": 3, "metric": "AIC"},   {"name": "M4: Competitive Strategy Avoidance", "family": "Rescorla-Wagner + opponent strategy avoidance", "n_params": 3, "metric": "AIC"} ]
- **model_mb_mf:** MF
- **model_params:** - $\alpha$ (learning rate): Mimicry M = .05 (SD = .10), Indifferent M = .07 (SD = .14) - c (sensitivity constant, transformed: $\theta = 3^{10 \cdot c - 1}$): Mimicry M = .26 (SD = .26), Indifferent M = .31 (SD = .26) - $\beta$ [S] (competition weight -- strategy avoidance): Mimicry M = .08 (SD = .11), Indifferent M = .02 (SD = .07); significantly different between conditions (p = .029, BF = 2.16)
- **social_param:** $\beta$ [S] -- competition parameter governing the weight assigned to avoiding the opponent's current choice strategy (opponent's choice proportion to alternative option over past 10 trials). Higher values indicate stronger opponent strategy avoidance.
- **social_param_name:** $\beta$
- **social_param_value:** 2.16
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC (specifically $\Delta$AIC between each learning model and stationary baseline); Bayesian t-tests and repeated-measures ANOVA on $\Delta$AIC across models
- **how_model_fit:** individual-level-fit (MLE via particle swarm optimization, 24 particles per individual)
- **data_type_fit_to:** choice behavior (trial-by-trial one-step-ahead prediction of binary choice sequence)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioural study only)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 50 (25 mimicry, 25 indifferent); 35 female; mean age 18.92 (SD = 1.19)
- **population_category:** healthy adults
- **population_age_range:** M=18.92 (SD=1.19)
- **ecological_validity:** Competition paradigm designed to mirror natural foraging situations (ideal free distribution logic). However, opponent is computerized with algorithm-determined behavior, not a real human competitor. Binary choice task is abstract (light bulbs) rather than naturalistic. Feedback structure (including optimal earnings display) is artificial.
- **eligibility_flag:** Borderline -- learning occurs over time (500 trials) and involves a social agent (computerized opponent), but the "social" dimension is competition against a computer, not genuine social learning. The computational modeling is present and applied to behavioral data. The core learning is about optimal choice strategy (matching vs. maximizing) rather than learning about social agents per se. Flag: borderline social learning -- competition against computerized opponent; learning is primarily about choice strategy optimization rather than social information.
- **concerns:** - The computerized opponent is not a real social agent; mimicry algorithm is deterministic given participant history - In Experiment 1, the three competitive RL models were not significantly different from each other, so "winning model" designation is tentative - No parameter recovery or model recovery analyses reported - No simulation of models prior to fitting (or at least not reported) - Win-stay lose-shift and small-sample heuristic models were tested but dismissed in a footnote without full reporting
- **limitations_reported:** the relative importance of these different competitive learning mechanisms remains ambiguous" (competitive models fit comparably well); "various levels of process complexity may have contributed to competitive probability matching"; extensions to face-to-face interactions and real human opponents are needed; the over-learning account of matching as transferred from competitive environments is speculative
- **limitations_categorized:** model identifiability; task simplicity; limited ecological validity (computerized opponent); limited generalizability (to real social interactions); speculative theoretical interpretation
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
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- spec_target = partly
- tax_domain_C_exchange_interdependence
- tax_domain_G_uncertainty_volatility
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_temperature
- tax_rr_primary_topic = competition
- tax_rr_secondary_topic = exploration_exploitation
- tax_rr_topic_competition
- tax_rr_topic_exploration_exploitation
- tax_topic_competition
- tax_topic_exploration_exploitation
