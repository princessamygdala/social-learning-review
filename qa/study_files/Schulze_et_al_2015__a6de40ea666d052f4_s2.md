# Schulze et al. (2015)

- **study_id:** `a6de40ea666d052f4_s2`
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
- **study_focus:** Competitive reinforcement learning under risk; how competition shapes probability matching vs. maximizing when outcome probabilities are known (described).
- **study_focus_short:** Competitive reinforcement learning under risk
- **learning_mode_description:** - Learning mode: Learning from competitive choice outcomes about optimal choice strategy under competition with known probabilities   - Learning from:     - Source type (social): other (computerized opponent)       - Joint: outcome is **joint**     - Source content (non-social): outcome (monetary payoff, jointly determined)   - Learning about:     - Target type (non-social): world (which strategy is optimal given opponent)     - Target content (non-social): action/policy (optimal choice strategy)
- **task_description:** Participants predicted the outcome of a 10-sided die (7 green, 3 red) over 300 trials, competing against a computerized opponent (mimicry or indifferent). Outcome probabilities were disclosed at the start; correct predictions earned 4 cents, split to 2 when both chose correctly.
- **task_paradigm:** Risky decision-making
- **players:** Single agent (participant), dyadic (computerized opponent; mimicry or indifferent)
- **n_players:** dyadic (2)
- **partner_type:** computer (algorithmic)
- **stimuli:** 10-sided die (7 green/3 red), RED/GREEN buttons, monetary payoffs (0/2/4 cents), opponent choice feedback
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Significant main effect of trial block (F(3.29, 157.72) = 9.78, p < .001, $\eta^2_p$ = .169, BF = 434716.13) - Significant main effect of competitor type (F(1, 48) = 5.16, p = .028, $\eta^2_p$ = .097, BF = 2.36) - Indifferent condition approached maximizing (M = .89 final block); mimicry condition over-matched (M = .81 final block, started at .72) - Participants facing indifferent opponents were 6.69 times more likely to maximize; mimicry participants 3.05 times more likely to match - Strategy Avoidance model significantly outperformed Individual RL (BF = 290.50), Payoff Comparison (BF = 1274.85), and Goal Separation (BF = 77.96)
- **effect_size:** $\eta^2_p$ = .169 (trial block), $\eta^2_p$ = .097 (competitor type), $\eta^2_p$ = .049 (interaction); OR = 6.69 (maximizing, indifferent), OR = 3.05 (matching, mimicry); BF = 2.36 (competitor type); BF = 290.50 (Strategy Avoidance vs. Individual RL)
- **learning_from:** Joint outcomes from own choice + opponent choice + die outcome; Source: other (opponent) + world (die)
- **learning_about:** Optimal choice policy given opponent type; Target: world/action policy  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** MEDIUM confidence -- Strategy Avoidance was numerically best but not significantly better than other competitive models in Experiment 1; it was only clearly superior in Experiment 2.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Stationary baseline", "family": "statistical", "n_params": 1, "metric": "AIC"},   {"name": "M1: Individual RL", "family": "Rescorla-Wagner", "n_params": 2, "metric": "AIC"},   {"name": "M2: Competitive Payoff Comparison", "family": "Rescorla-Wagner + inequity aversion", "n_params": 3, "metric": "AIC"},   {"name": "M3: Competitive Goal Separation", "family": "Rescorla-Wagner + dual-goal utility", "n_params": 3, "metric": "AIC"},   {"name": "M4: Competitive Strategy Avoidance", "family": "Rescorla-Wagner + opponent strategy avoidance", "n_params": 3, "metric": "AIC"} ]
- **model_mb_mf:** MF
- **model_params:** LOW confidence for exact Table 4 values -- the OCR did not cleanly render Table 4; values are taken from text discussion. - **$\beta$ competition parameter significance (Study 2)**: LOW confidence -- BF = 1.46 is anecdotal evidence only.  ### CANNOT FIND  - Exact Table 2 DAIC values for Experiment 1 (table was not rendered in OCR) - Exact Table 4 values for Experiment 2 (table rendering issues in OCR) - Parameter recovery or model recovery analyses (not conducted) - Simulation studies (not reported) - Data/code availability statement  ### OTHER NOTES  - No supplement file found for this paper. - The paper includes two additional models mentioned only in footnotes: a win-stay lose-shift heuristic (2 params) and a small-sample-of-experience model (1 param), both of which performed worse than the stationary baseline and are not considered further. This reduces transparency of the full modeling enterprise. - The paper also references supplementary non-competitive baseline experiments (Footnote 5) run on the same participant pool, but these are not described in detail. - The OCR quality of this text file is poor (spaces removed within words, special characters replaced with codes like "(cid:2)" for minus signs, "(cid:6)" for multiplication), but all key information was extractable. - The paper presents a fundamentally game-theoretic perspective on probability matching, bridging behavioral ecology (ideal free distribution) and reinforcement learning. The social component is the com
- **social_param:** $\beta$ [S] -- competition parameter governing weight of opponent strategy avoidance in choice rule. Significantly higher in mimicry than indifferent condition.
- **social_param_name:** $\beta$ [S]
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC ($\Delta$AIC); Bayesian t-tests; repeated measures ANOVA
- **how_model_fit:** individual-level-fit (MLE via particle swarm optimization)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 50 (25 mimicry, 25 indifferent); 29 female; mean age 19.00 (SD = 2.19)
- **population_category:** healthy adults
- **population_age_range:** M=19.00 (SD=2.19)
- **ecological_validity:** Same concerns as Experiment 1. Slight improvement: described probabilities (die) are more ecologically plausible than unknown light bulbs, but still abstract. Computerized, not human, opponent.
- **eligibility_flag:** Borderline social learning. The opponent is computerized (not a real social agent). Learning is primarily about optimal choice strategy in a competitive environment, not about social information per se. The social dimension is the competitive structure (opponent whose behavior depends on/is independent of participant behavior). MEDIUM confidence that this qualifies as social learning.
- **concerns:** Same as Study 1. Additionally: Individual RL model performed worse than stationary baseline (negative $\Delta$AIC), suggesting limited trial-by-trial learning when probabilities are known. Competition parameter for Strategy Avoidance model only marginally significant (p = .049, BF = 1.46 -- weak evidence).
- **limitations_reported:** Same as Study 1 (shared General Discussion). "The overall performance of all evaluated learning models was lower than reported for Experiment 1"; extension to face-to-face interactions needed; competitive mechanisms remain partially ambiguous.
- **limitations_categorized:** model identifiability; task simplicity; limited ecological validity; weak statistical evidence for key parameter; limited generalizability
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
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_temperature
- tax_rr_primary_topic = competition
- tax_rr_topic_competition
- tax_topic_competition
